# SheetMetalFolder2

Extension of the ISheetMetalFolder interface to change thickness and radius value (SolidWorks Bug)



# Usage

 

        public void Main()
        {
          
            ModelDoc2 swModelDoc = (ModelDoc2)swApp.ActiveDoc;
            SelectionMgr swSelectionManager = (SelectionMgr)swModelDoc.SelectionManager;
            Feature swFeature = (Feature)swSelectionManager.GetSelectedObject6(1,-1);
            SheetMetalFolder swSheetMetalFolder = (SheetMetalFolder)swFeature.GetSpecificFeature2();



            // Declare swSheetMetalFolder2 using decorator pattern
            SheetMetalFolder2 swSheetMetalFolder2  = new SheetMetalFolder2(swSheetMetalFolder);
            // change thickness 
            swSheetMetalFolder2.Thickness(20);

            // change bend radius
            swSheetMetalFolder2.BendRadius(3);

            // rebuild is necessary to get effects
            swModelDoc.ForceRebuild3(true);
        }

        /// <summary>
        ///  The SldWorks swApp variable is pre-assigned for you.
        /// </summary>
        public SldWorks swApp;

#Credits 

Credits goes to the following gentlemen for this methodology: Artem Taturevych and Viktor Bovzdarenko. You can find them at the SolidWorks Forums (API Section).

# Update
This bug was resolved in Solidworks 2017 b2.
