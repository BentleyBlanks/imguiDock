# imguiDock
An addon of [imgui](https://github.com/ocornut/imgui/wiki) for support dock in the window

# Intro
Thx to the [nem0](https://github.com/nem0), [paniq](https://github.com/paniq), [adcox](https://github.com/adcox)'s distribute of ```imgui_dock```, so the imgui_dock was able to ```auto save/load``` to/from the ```imgui.ini```.

<a data-flickr-embed="true"  href="https://www.flickr.com/photos/134486032@N03/24660622177/in/dateposted-public/" title="QQ图片20180106100302"><img src="https://farm5.staticflickr.com/4683/24660622177_7dafeee6e1_c.jpg" width="800" height="621" alt="QQ图片20180106100302"></a>

> It seems the [Lumix Engine](https://github.com/nem0/LumixEngine) have done a quite intelligible work just save the dock's property to a Lua file, so I was just save the properties to the ```imgui.ini```.(you can modify the format if your want)

# How to use
```cpp
void setup(){
	// auto-load the imgui.ini settings
	ImGui::InitDock();
}

void update(){
	if(ImGui::Begin("Dock Demo"))
	{
		// dock layout by hard-coded or .ini file
		ImGui::BeginDockspace();

		if(ImGui::BeginDock("Dock 1")){
			ImGui::Text("Hi");
		}
		ImGui::EndDock();

		if(ImGui::BeginDock("Dock 2")){
			ImGui::Text("I'm BentleyBlanks!");
		}
		ImGui::EndDock();

		if(ImGui::BeginDock("Dock 3")){
			ImGui::Text("Hello World");
		}
		ImGui::EndDock();

		ImGui::EndDockspace();
	}
	ImGui::End();
}

```

> Some complie errors may occured because of the API change of ImGui, pls let me know