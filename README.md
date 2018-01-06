# imguiDock
An addon of [imgui](https://github.com/ocornut/imgui/wiki) for support dock in the window

# Intro
Thx to the [nem0](https://github.com/nem0), [paniq](https://github.com/paniq), [adcox](https://github.com/adcox)'s distribute of ```imgui_dock```, I've added the function of ```load/save``` to the [imgui_dock](https://github.com/adcox/imgui/blob/master/imgui_dock.h)(but not auto saving).

<a data-flickr-embed="true"  href="https://www.flickr.com/photos/134486032@N03/24660622177/in/dateposted-public/" title="QQ图片20180106100302"><img src="https://farm5.staticflickr.com/4683/24660622177_7dafeee6e1_c.jpg" width="800" height="621" alt="QQ图片20180106100302"></a>

> It seems the [Lumix Engine](https://github.com/nem0/LumixEngine) have done a quite intelligible work just save the dock's property to a Lua file, so I was just translate it to a .ini file named ```imgui_dock.ini```.(you can modify the format if your want)

# How to use
```cpp
void setup(){
	// load the imgui_dock.ini settings
	ImGui::LoadDock();
}

void update(){
	if(ImGui::Begin("Dock Demo"))
	{
		// dock layout by hard-coded or .ini file
		ImGui::BeginDockspace();

    	if(ImGui::BeginDock("Dock 1"))
	    {
	    	ImGui::Text("Hi");
	    }
	    ImGui::EndDock();

	    if(ImGui::BeginDock("Dock 2"))
	    {
	        ImGui::Text("I'm BentleyBlanks!");
	    }
	    ImGui::EndDock();

	    if(ImGui::BeginDock("Dock 3"))
	    {
	        ImGui::Text("Hello World");
	    }
	    ImGui::EndDock();

	    ImGui::EndDockspace();
	}
    ImGui::End();
}

...
// In some cases save the layout of dock to imgui_dock.ini
ImGui::LoadDock();
...

```