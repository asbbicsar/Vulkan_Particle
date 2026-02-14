# Vulkan Project

이 프로젝트는 Vulkan API를 사용한 그래픽스 프로젝트입니다. 저장소 용량 최적화와 이식성을 위해 Vulkan SDK는 포함되어 있지 않으며, 환경 변수를 통해 로컬 SDK를 참조합니다.

---

## 🛠 Prerequisites (사전 준비) - Korean

### 1. Vulkan SDK 설치
* [Vulkan 공식 사이트 (LunarG)](https://vulkan.lunarg.com/sdk/home)에서 OS에 맞는 최신 버전을 다운로드하여 설치합니다.
* 설치 시 기본 경로를 사용하는 것을 권장합니다.

### 2. 환경 변수 확인
설치가 완료되면 시스템 환경 변수에 `VULKAN_SDK`가 자동으로 등록됩니다. 터미널(CMD)에서 아래 명령어로 확인 가능합니다:
```bash
echo %VULKAN_SDK%

```

> **참고:** 경로가 출력되지 않는다면, SDK 설치 폴더를 직접 시스템 환경 변수 `VULKAN_SDK`로 등록해야 합니다.

### 3. Visual Studio 프로젝트 설정

본 프로젝트는 절대 경로 대신 **매크로(Macro)**를 사용하여 어디서든 즉시 빌드가 가능합니다:

* **Include:** `$(VULKAN_SDK)\Include`
* **Library:** `$(VULKAN_SDK)\Lib`
* **Linker Input:** `vulkan-1.lib`

---

## 🛠 Prerequisites - English

This project requires the **Vulkan SDK**. To keep the repository lightweight and portable, the SDK files are not included directly. Please follow the steps below to set up your environment.

### 1. Install Vulkan SDK

* Download and install the latest version of the Vulkan SDK from the [LunarG Official Website](https://vulkan.lunarg.com/sdk/home).
* It is highly recommended to use the default installation path.

### 2. Verify Environment Variables

After installation, verify that the `VULKAN_SDK` environment variable is set by running the following command in your terminal (CMD):

```bash
echo %VULKAN_SDK%

```

> **Note:** If the path does not appear, you must manually set the `VULKAN_SDK` system environment variable to your SDK installation folder.

### 3. Visual Studio Configuration

This project uses **Macros** instead of absolute paths for seamless collaboration:

* **Include Directories:** `$(VULKAN_SDK)\Include`
* **Library Directories:** `$(VULKAN_SDK)\Lib`
* **Linker Input:** `vulkan-1.lib`

---

## 🚀 Getting Started

1. **Clone** this repository:
```bash
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)

```


2. Ensure that other external libraries (GLFW, GLM) are located in the `external/` directory as configured.
3. Open the `.sln` file in Visual Studio.
4. Set the solution platform to **x64**.
5. **Build (Ctrl + Shift + B)** and Run.

---

### 💡 Note on SDK Exclusion

Vulkan SDK는 용량이 크고 사용자 환경(OS/Driver)에 따라 다르기 때문에 저장소에 포함하지 않습니다. 대신 `$(VULKAN_SDK)` 매크로를 활용하여 로컬에 설치된 SDK를 참조하도록 설계되었습니다.

```
