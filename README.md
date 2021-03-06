Create [Dear ImGui](https://github.com/ocornut/imgui) application easily on Windows

## Example

```c++
#include "imguiWin.h"

class application :public imguiWin {
	 
  virtual ImGuiContext* onCreate(HWND hwnd) {
    IMGUI_CHECKVERSION();
    ImGuiContext* ctx = ImGui::CreateContext();
    return ctx;
  }

  virtual ImDrawData* onRender() {
    ImGui::NewFrame();
    
    ImGui::Begin("imguiWin example");
    ImGui::Text("Hello world!");
    ImGui::End();
    
    ImGui::Render();
    return ImGui::GetDrawData();
  }

  void onDestroy() {
    ImGui::DestroyContext();
  }
};

int APIENTRY WinMain(HINSTANCE, HINSTANCE, LPSTR, int) {
  application app;
  return app.run("imguiWin example");
}
```

![](https://github.com/smok95/imguiWin/blob/master/screenshot.png)

## Release
https://github.com/smok95/imguiWin/releases/tag/v0.0.1
