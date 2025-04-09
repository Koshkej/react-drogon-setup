![banner](https://github.com/user-attachments/assets/3a55cba2-3988-4ab9-8093-857a17ffa455)

Automated script for rapid fullstack project initialization with modern stack:
- **Frontend**: React 18 (Webpack 5 + Babel 7)
- **Backend**: [Drogon Framework](https://github.com/drogonframework/drogon) (C++20 HTTP-server)
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

- GitHub: [drogonframework/drogon](https://github.com/drogonframework/drogon)
- Documentation: [Drogon Website](https://drogon.org/)
- Community: [GitHub Discussions](https://github.com/drogonframework/drogon/discussions)

#### Core Features

🟣 Creates 3-in-1 project structure:

- `/frontend` - React app with preconfigured setup
- `/backend` - Drogon server with proper CMake configuration
- `/deploy` - Shared directory for production artifacts

🟣 Automatic configuration:

- Installs Drogon (if missing)
- Configures Webpack for production/development builds
- Generates basic React components (App, index)
- Sets up CORS and static file serving through Drogon

🟣 Workflow optimization:
   
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

Ubuntu/Debian or compatible, Node.js 16.x+, npm 8.x+, CMake 3.15+, gcc/g++ 11.x+ <br>
**Sudo privileges for Drogon installation**

#### Installation

**[1] Download script:**

```bash
wget https://your-domain.com/path/to/bush
```

**[2] Make executable:**
   
```bash
chmod +x bush
```

**[3] (Optional) Add to PATH:**

```bash
sudo mv bush /usr/local/bin/
```
   
### Usage

Basic execution:

```bash
create-react-drogon my_project
```

After completion you'll see:

```bash
✅ Project "my_project" created successfully!

Next steps to run your project:

1. Build the React application:
   cd my_project/frontend && npm run build
   This will compile your React code and output 'main.js' into the deploy directory.

2. Build the Drogon project:
   cd my_project/backend && mkdir -p build && cd build && cmake .. && make
   The server executable will be placed in the deploy directory.

3. Run the Drogon server:
   From the deploy directory, run the executable (e.g., ./your_executable_name).

4. Open your browser and navigate to: http://localhost:5555/
   You should see the React application served by Drogon.
```

### Creation Process Details

Script executes sequentially:

#### [1] Argument validation:

- Checks project name presence
- Verifies directory doesn't exist

#### [2] Structure creation:
   
```bash
my_project/
├── frontend/
│   ├── src/              # React sources
│   ├── webpack.config.js # Production optimizations
│   └── babel.config.json # JSX support
├── backend/
│   ├── CMakeLists.txt    # Pre-configured build
│   └── main.cc           # Server listening on :5555
└── deploy/
    ├── index.html        # Entry point
    ├── main.js           # ReactJS compiled app
    └── my_project        # Compiled executable
```

#### [3] Drogon setup:

- Auto-install via apt
- CMake patching for /deploy output
- Basic HTTP server example

#### [4] React initialization:

- Dependency installation (react, webpack, babel)
- Preconfigured JSX rules
- Ready-to-use npm scripts

### Project Workflow

#### Frontend Development

Start dev server with hot reload:

```bash
cd frontend
npm run dev
```

**Features:**

- Auto-rebuild on changes
- Source maps for debugging
- API request proxying to Drogon

#### Backend Development

Build and run:

```bash
cd backend
mkdir -p build && cd build
cmake ..
make
```

### Production Build

#### [1] Build frontend:

```bash
cd frontend
npm run build # ⇒ /deploy/main.js
```

#### [2] Build backend:

```bash
cd backend/build
make clean && make
```

#### [3] Run server:

```bash
cd deploy
./my_project
```
