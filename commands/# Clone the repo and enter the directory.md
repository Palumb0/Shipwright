# Clone the repo and enter the directory
git clone https://github.com/HarbourMasters/Shipwright.git
cd Shipwright

# Clone the submodules
git submodule update --init

# Generate Ninja project
cmake -H. -Bbuild-cmake -GNinja # -DCMAKE_BUILD_TYPE:STRING=Release (if you're packaging) -DPython3_EXECUTABLE=$(which python3) (if you are using non-standard Python installations such as PyEnv)

# Generate soh.otr
cmake --build build-cmake --target GenerateSohOtr

# Compile the project
cmake --build build-cmake # --config Release (if you're packaging)

# Now you can run the executable in ./build-cmake/soh/soh.elf
# To develop the project open the repository in VSCode (or your preferred editor)