![banner](https://github.com/user-attachments/assets/3a55cba2-3988-4ab9-8093-857a17ffa455)

Automated script for rapid fullstack project initialization with modern stack:
- **Frontend**: React 18 (Webpack 5 + Babel 7)
- **Backend**: [Drogon Framework](https://github.com/drogonframework/drogon) (C++17 HTTP-server)
- **Infrastructure**: Automated build and deployment

### What does this script do?

#### About Drogon

Drogon is a high-performance C++17/20 HTTP application framework. Key features:

- Async/non-blocking architecture
- Built-in HTTP/1.1 and WebSocket support
- Cross-platform (Linux/macOS/Windows)
- ORM and template engine support
- Used in production by Tencent, Alibaba, and others

Official Resources:

> - GitHub: [drogonframework/drogon](https://github.com/drogonframework/drogon)
> - Documentation: [Drogon Website](https://drogon.org/)
> - Community: [GitHub Discussions](https://github.com/drogonframework/drogon/discussions)

#### Core Features
1. Creates 3-in-1 project structure:
   - `/frontend` - React app with preconfigured setup
   - `/backend` - Drogon server with proper CMake configuration
   - `/deploy` - Shared directory for production artifacts

2. Automatic configuration:
   - Installs Drogon (if missing)
   - Configures Webpack for production/development builds
   - Generates basic React components (App, index)
   - Sets up CORS and static file serving through Drogon

3. Workflow optimization:
   - Configures output directory for Drogon binaries
   - Creates HTML template for React app
   - Generates convenient NPM scripts

### Why use this?

✔️ Saves time of initial setup  
✔️ Eliminates configuration errors  
✔️ Production-ready template  
✔️ Modern toolchain integration  
✔️ Optimal build configurations

### Complete Guide

#### Requirements
1. **OS**: Ubuntu/Debian or compatible
2. **Minimum versions**:
   - Node.js 16.x+
   - npm 8.x+
   - CMake 3.15+
   - gcc/g++ 11.x+
3. sudo privileges for Drogon installation

#### Installation

1. Download script:

```bash
wget https://your-domain.com/path/to/bush
```

2. Make executable:
   
```bash
chmod +x bush
```

4. (Optional) Add to PATH:

```bash
sudo mv bush /usr/local/bin/
```
   
#### Usage

Basic execution:

```bash
./bush my_project
```

After completion you'll see:

```bash
✅ Project "my_project" created successfully!

Next steps:
1. Build React: cd my_project/frontend && npm run build
2. Compile Drogon: cd my_project/backend && mkdir build && cd build && cmake .. && make
3. Run server: cd ../deploy && ./my_project
```

#### Creation Process Details

Script executes sequentially:

1. Argument validation:

- Checks project name presence
- Verifies directory doesn't exist

2. Structure creation:
   
```bash
my_project/
├── frontend/
│ ├── src/              # React sources
│ ├── webpack.config.js # Production optimizations
│ └── babel.config.json # JSX support
├── backend/
│ ├── CMakeLists.txt    # Pre-configured build
│ └── main.cc           # Server listening on :8080
└── deploy/
├── index.html          # Entry point
├── main.js             # ReatJS complied app
└── my_project          # Compiled executable
```

3. Drogon setup:

- Auto-install via apt
- CMake patching for /deploy output
- Basic HTTP server example

4. React initialization:

- Dependency installation (react, webpack, babel)
- Preconfigured JSX rules

Ready-to-use npm scripts

#### Project Workflow

**Frontend Development**

Start dev server with hot reload:

```bash
cd frontend
npm run dev # -> http://localhost:8081
```

Features:

-Auto-rebuild on changes
- Source maps for debugging
- API request proxying to Drogon

**Backend Development**

Build and run:

```bash
cd backend
mkdir -p build && cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
make -j4
```

Move binary:

```bash
cp my_project ../../deploy/
```

#### Production Build

**Build frontend:**

```bash
cd frontend
npm run build # ⇒ /deploy/main.js
```

**Build backend:**

```bash
cd backend/build
make clean && make -j4
```

**Run server:**

```bash
cd deploy
./my_project # Server on :8080
```
