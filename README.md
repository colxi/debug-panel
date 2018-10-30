## Debug Panel

Boilerplate container for debugging purposes.
A handy and non intrusive (shadow root) panel, resizable, foldable and easilly configurable with custom tabs & action shortcut icons. 




```javscript

    import {debugPanel} from './node_modules/debug-panel/src/debugger.js';

    // load custom styles
    debugPanel.loadStyles( 'my-custom-style.css' );

    //Register new tabs
    let tabId = debugPanel.Register.tab( 'File Info', (view)=>{
        view.innerHTML='test' 
    })
    // Or register new actions (shirtcut icons)...
    debugPanel.Register.action( 'Alert', '!' , ()=>{
        alert('test')
    })


    // add native features, like a dom selector tab...
    debugPanel.addFeature.tab.DOMSelector();
    // or a shortcut icon lo load files
    debugPanel.addFeature.action.fileOpen(
        e=>{ alert('file selected' ) },
        { accept: '.png' }
    );

	// update current tab
	Debug.updateTab();
    // fold and unfold
    debugPanel.fold();
    debugPanel.unfold();
	
    // load a registered tab
    debugPanel.openTab(tabId)
 
``` 