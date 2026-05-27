# ── Stage 1: Build ───────────────────────────────────────────────
FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
WORKDIR /src

# Install clang for native compilation
RUN apt-get update && apt-get install -y clang zlib1g-dev

COPY MyApp.csproj ./
RUN dotnet restore MyApp.csproj

COPY . .
RUN dotnet publish MyApp.csproj -c Release -r linux-x64 \
    --self-contained true \
    -p:PublishSingleFile=true \
    -o /app/publish

# ── Stage 2: Run ─────────────────────────────────────────────────
FROM busybox
COPY --from=build /app/publish/MyApp /hello-binary
CMD ["/hello-binary"]