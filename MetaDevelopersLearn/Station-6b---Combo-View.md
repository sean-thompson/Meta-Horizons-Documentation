# Station 6b - Combo View

[source](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/custom-ui-examples-tutorial/station-6b-combo-view)

This station demonstrates how you can combine multiple nested view objects to assemble groups of elements in your user interface.

In the previous example, the `View()` objects were created as constructors, which allows them to be referenced multiple times. Since the entire column was created as a constructor, it can be reused as well, which results in the side-by-side Flex Column objects in the following image.

In this manner, you can build sophisticated user interfaces by assembling core UI widgets as constructor `View()` objects and combining them together to build more sophisticated objects, which can be referenced from a library. Think, for example, of a Confirmation Dialog created as a set of constructor `View()` objects.

![Image of Station 6b](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475767631_646003161270972_6759271736042486324_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=oxa3WN45EEoQ7kNvwEpTbze&_nc_oc=AdkmOQGYthMGewHCIaU1GUri7-q9g8aY4r5HTAfBkzCWC8rSbiSCGJSqTZmWY7fobJ0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8mjKXRQ1649suOGRHSyyhQ&oh=00_AfSR-SgTyA4cTHZ4MhyY2lb0COZJh_NL8LUqgT_k_vw95A&oe=689BACD6)

## Assets

*   **Station06b-CustomUI: CustomUI gizmo**
    
    *   Visible: true
    
    *   Script: the script that defines the custom UI elements must be attached.

*   **Station06b-ComboView: script**
    
    *   This script defines the customUI object and loads referenced objects.

## Script

### Station06b-ComboView

*   This script includes more constructor `View()` object declarations: The structure of the UI is as follows:
    
    *   UIComponentViewCombo class
        
        *   `Text()`
        
        *   `viewNestedCombo()`: `flexDirection = "column"` *   `viewNestedRow()`: `flexDirection = "row"` *   `Text()`
                    
                     instance
                
                *   `viewSimple()`: `flexDirection` is not specified
                    
                    *   `Text()`
                        
                         instance
                    
                    *   `MyButton()`
                        
                         instance
                
                *   `MyButton()`
                    
                     instance
                
                *   `viewSimple()`:
                    
                    *   `Text()`
                        
                         instance
                    
                    *   `MyButton()`
                        
                         instance
            
            *   `View()`
                
                 instance: This view is declared inline and not as a constructor
                
                *   `viewNestedCol()`: `flexDirection = "column"` *   `Text()`
                        
                         instance
                    
                    *   `viewSimple()`: `flexDirection` is not specified
                        
                        *   `Text()`
                            
                             instance
                        
                        *   `MyButton()`
                            
                             instance
                    
                    *   `viewSimple()`: `flexDirection` is not specified
                        
                        *   `Text()`
                            
                             instance
                        
                        *   `MyButton()`
                            
                             instance
                    
                    *   `ViewBorder()`: `flexDirection` is not specified
                        
                        *   `Text()`
                            
                             instance
                
                *   `viewNestedCol()`: `flexDirection = "column"` *   `Text()`
                        
                         instance
                        
                    
                    *   `viewSimple()`: `flexDirection` is not specified
                        
                        *   `Text()`
                            
                             instance
                        
                        *   `MyButton()`
                            
                             instance
                    
                    *   `viewSimple()`: `flexDirection` is not specified
                        
                        *   `Text()`
                            
                             instance
                        
                        *   `MyButton()`
                            
                             instance
                    
                    *   `ViewBorder()`: `flexDirection` is not specified
                        
                        *   `Text()`
                            
                             instance
                
                *   `viewNestedCol()`: `flexDirection = "column"` *   `Text()`
                        
                         instance
                    
                    *   `viewSimple()`: `flexDirection` is not specified
                        
                        *   `Text()`
                            
                             instance
                        
                        *   `MyButton()`
                            
                             instance
                    
                    *   `viewSimple()`: `flexDirection` is not specified
                        
                        *   `Text()`
                            
                             instance
                        
                        *   `MyButton()`
                            
                             instance
                    
                    *   `ViewBorder()`: `flexDirection` is not specified
                        
                        *   `Text()`
                            
                             instance

## Key Learnings

### Meta Horizon Worlds learnings

*   Building combinations of constructor `View()` objects to assemble more complex interfaces.

### TypeScript coding

*   None.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 