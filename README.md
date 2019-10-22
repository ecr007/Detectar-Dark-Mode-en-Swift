# Detectar-Dark-Mode-en-Swift

```swift
// MARK: Set Color Mode
	func setColorMode(){
		
		let colorForDarkModeWeb:String = "var style = document.createElement('style'); style.innerText = 'body{background-color:#1f1e1f !important;color:#fff !important;} #cphCuerpo_gvDatos table{background-color:#1f1e1f !important;color:#fff !important;} #cphCuerpo_gvDatos tr{background-color:#1f1e1f !important;color:#fff !important;} #cphCuerpo_gvDatos td{background-color:#1f1e1f !important;color:#fff !important;} b{color:#fff !important;} ';document.head.append(style);"
		
		let colorForLightModeWeb:String = "var style = document.createElement('style'); style.innerText = 'body{background-color:#fff !important;color:#000 !important;} #cphCuerpo_gvDatos table{background-color:#fff !important;color:#000 !important;} #cphCuerpo_gvDatos tr{background-color:#fff !important;color:#000 !important;} #cphCuerpo_gvDatos td{background-color:#fff !important;color:#000 !important;} b{color:#333 !important;} '; document.head.append(style);"
				
		if #available(iOS 13, *), self.traitCollection.userInterfaceStyle == .dark{
			self.web.stringByEvaluatingJavaScript(from: colorForDarkModeWeb)
			self.objLoading.color = .white
		}
		else{
			self.web.stringByEvaluatingJavaScript(from: colorForLightModeWeb)
			self.objLoading.color = .gray
		}
	}
	
	override func traitCollectionDidChange(_ previousTraitCollection: UITraitCollection?) {
      setColorMode()
  }
  ```
