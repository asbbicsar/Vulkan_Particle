🛠 Prerequisites (사전 준비)
이 프로젝트는 Vulkan SDK를 포함하고 있지 않습니다. 빌드 전 아래 단계를 따라 로컬 환경을 설정해 주세요.

1. Vulkan SDK 설치
Vulkan 공식 사이트 (LunarG)에서 OS에 맞는 최신 버전을 다운로드하여 설치합니다. (Windows 추천)

설치 시 "기본 경로"에 설치하는 것을 권장합니다.

2. 환경 변수 확인
Vulkan SDK를 설치하면 시스템 환경 변수에 VULKAN_SDK가 자동으로 등록됩니다. 터미널(CMD)에서 아래 명령어로 확인 가능합니다.

Bash
echo %VULKAN_SDK%
참고: 만약 경로가 출력되지 않는다면, SDK 설치 폴더를 직접 시스템 환경 변수 VULKAN_SDK로 등록해야 합니다.

3. Visual Studio 프로젝트 설정
본 프로젝트는 절대 경로 대신 매크로를 사용하도록 설정되어 있습니다. 별도의 경로 수정 없이 바로 빌드가 가능합니다.

Include: $(VULKAN_SDK)\Include

Library: $(VULKAN_SDK)\Lib

Linker Input: vulkan-1.lib 추가됨

🚀 Getting Started
이 저장소를 Clone 합니다.

external/ 폴더 내에 필요한 라이브러리(GLFW, GLM 등)가 있는지 확인합니다.

.sln 파일을 열고 x64 모드에서 빌드(Ctrl + Shift + B)를 수행합니다.

💡 팁: 왜 SDK를 포함하지 않나요?
Vulkan SDK는 용량이 매우 크고 사용자의 OS 및 드라이버 버전에 의존적입니다. 따라서 보안과 저장소 효율을 위해 직접 포함하는 대신, 사용자의 시스템 환경 변수($(VULKAN_SDK))를 참조하도록 설계되었습니다.

🛠 Prerequisites
This project requires the Vulkan SDK. To keep the repository lightweight and portable, the SDK files are not included directly in the repository. Please follow the steps below to set up your environment.

1. Install Vulkan SDK
Download and install the latest version of the Vulkan SDK from the LunarG Official Website.

It is highly recommended to use the default installation path.

2. Verify Environment Variables
After installation, the installer should automatically add the VULKAN_SDK environment variable to your system. You can verify this by running the following command in your terminal (CMD):

Bash
echo %VULKAN_SDK%
Note: If the path does not appear, you must manually set the VULKAN_SDK system environment variable to your SDK installation folder.

3. Visual Studio Configuration
This project is configured to use Macros instead of absolute paths. This allows the project to be built on any machine without modifying project settings:

Include Directories: $(VULKAN_SDK)\Include

Library Directories: $(VULKAN_SDK)\Lib

Linker Input: vulkan-1.lib is already linked.

🚀 Getting Started
Clone this repository:

Bash
git clone https://github.com/asbbicsar/Vulkan_Particle.git
Ensure that the required headers and binaries (GLFW, GLM) are located in the external/ directory.

Open the .sln file in Visual Studio.

Set the solution platform to x64.

Build (Ctrl + Shift + B) and Run.

💡 Why is the SDK not included?
The Vulkan SDK is large and platform-dependent. To ensure repository efficiency and security, we use the $(VULKAN_SDK) macro to reference the SDK installed on your local system. This ensures the project remains lightweight and easy to manage via Git.
