Map.setOptions('Satellite')
Map.style().set('cursor','crosshair');
Map.centerObject(geometry,12)

//print(table1)
//var shapefile = ee.FeatureCollection('users/aanand0214/shapefile');
//Map.addLayer(table,{color: 'red'},'Gulf of Mannar');

//var shapefile = ui.Map.Layer(table, {color: 'red'},'shapefile',false )
//Map.add(shapefile)

//Map.addLayer(table,{color: 'red'},'Apt')

//var shapefile = ee.FeatureCollection('users/aanand0214/WII/aptenodytesforsteri');

//Map.addLayer(table1,{color: 'red'},'Apt');


var pygo = ee.FeatureCollection('users/aanand0214/WII/Pygoscelis_adeliae');
//Map.addLayer(pygo,{color: 'yellow'},'Pygo');

var apt = ee.FeatureCollection('users/aanand0214/WII/Aptenodytes_forsteri');
//Map.addLayer(apt,{color: 'red'},'Apt');

var dapt = ee.FeatureCollection('users/aanand0214/WII/Daption_capense');
//Map.addLayer(dapt,{color: 'orange'},'Dapt');

var fulm = ee.FeatureCollection('users/aanand0214/WII/Fulmarus_glacialoides');
//Map.addLayer(fulm,{color: 'orange'},'Fulm');

var macro = ee.FeatureCollection('users/aanand0214/WII/Macronectes_giganteus');
//Map.addLayer(macro,{color: 'orange'},'macro');

var ocea = ee.FeatureCollection('users/aanand0214/WII/Oceanites_oceanicus');
//Map.addLayer(ocea,{color: 'orange'},'ocea');

var pago = ee.FeatureCollection('users/aanand0214/WII/Pagodroma_nivea');
//Map.addLayer(pago,{color: 'orange'},'pago');

var phoe = ee.FeatureCollection('users/aanand0214/WII/Phoebetria_palpebrata');
//Map.addLayer(phoe,{color: 'orange'},'phoe');

var ster = ee.FeatureCollection('users/aanand0214/WII/Stercorarius_maccormicki');
//Map.addLayer(ster,{color: 'orange'},'ster');

var thal = ee.FeatureCollection('users/aanand0214/WII/Thalassoica_antarctica');
//Map.addLayer(thal,{color: 'orange'},'thal');



// Intialise the app

var inspectorPanel = ui.Panel({style:{width: '15%'}})
ui.root.insert(1,inspectorPanel);

var header = ui.Label('Mapping Antarctic Biodiversity',
{fontSize: '25px',
fontWeight: 'bold',
color: '#000080'
  
})

var text = ui.Label('text' ,
{fontSize: '15px',
textAlign: 'justify'
})

inspectorPanel.add(header).add(text)

var select = ui.Label({
  value: 'Select Seabird Species',
  style: {fontSize: '15px', fontWeight: 'bold'}
})

inspectorPanel.add(select)



var checkbox1 = ui.Checkbox('Pygoscelis Adeliae', false);
inspectorPanel.add(checkbox1)

checkbox1.onChange(function(checked) {
  // Shows or hides the first map layer based on the checkbox's value.
  Map.layers().get(0).setShown(checked);
});

Map.addLayer(pygo,{color: 'yellow'},'Pygo',false);

//Map.addLayer(ee.FeatureCollection('users/aanand0214/WII/Pygoscelis_adeliae'));
//print(checkbox);


var checkbox2 = ui.Checkbox('Aptenodytes Forsteri', false);
inspectorPanel.add(checkbox2)

checkbox2.onChange(function(checked) {
  // Shows or hides the first map layer based on the checkbox's value.
  Map.layers().get(1).setShown(checked);
});

Map.addLayer(apt,{color: 'red'},'Apt',false);


var checkbox3 = ui.Checkbox('Daption Capense', false);
inspectorPanel.add(checkbox3)

checkbox3.onChange(function(checked) {
  // Shows or hides the first map layer based on the checkbox's value. 
  Map.layers().get(2).setShown(checked); 
});

Map.addLayer(dapt,{color: 'orange'},'Dapt',false);



var checkbox4 = ui.Checkbox('Fulmarus Glacialoides', false);
inspectorPanel.add(checkbox4)

checkbox4.onChange(function(checked) {
  // Shows or hides the first map layer based on the checkbox's value. 
  Map.layers().get(3).setShown(checked); 
});

Map.addLayer(fulm,{color: 'Khaki'},'Fulm',false);                                         //F0E68C


var checkbox5 = ui.Checkbox('Macronectes Giganteus', false);
inspectorPanel.add(checkbox5)

checkbox5.onChange(function(checked) {
  // Shows or hides the first map layer based on the checkbox's value. 
  Map.layers().get(4).setShown(checked); 
});

Map.addLayer(macro,{color: 'Magenta'},'Macro',false);


var checkbox6 = ui.Checkbox('Oceanites Oceanicus', false);
inspectorPanel.add(checkbox6)

checkbox6.onChange(function(checked) {
  // Shows or hides the first map layer based on the checkbox's value. 
  Map.layers().get(5).setShown(checked); 
});

Map.addLayer(ocea,{color: 'lime'},'Ocea',false);


var checkbox7 = ui.Checkbox('Pagodroma Nivea', false);
inspectorPanel.add(checkbox7)

checkbox7.onChange(function(checked) {
  // Shows or hides the first map layer based on the checkbox's value. 
  Map.layers().get(6).setShown(checked); 
});

Map.addLayer(pago,{color: 'Aquamarine'},'Pago',false);


var checkbox8 = ui.Checkbox('Phoebetria Palpebrata', false);
inspectorPanel.add(checkbox8)

checkbox8.onChange(function(checked) {
  // Shows or hides the first map layer based on the checkbox's value. 
  Map.layers().get(7).setShown(checked); 
});

Map.addLayer(phoe,{color: 'Gold'},'Phoe',false);                                         


var checkbox9 = ui.Checkbox('Stercorarius Maccormicki', false);
inspectorPanel.add(checkbox9)

checkbox9.onChange(function(checked) {
  // Shows or hides the first map layer based on the checkbox's value. 
  Map.layers().get(8).setShown(checked); 
});

Map.addLayer(ster,{color: 'Blue'},'Ster',false);                                        


var checkbox10 = ui.Checkbox('Thalassoica Antarctica', false); 
inspectorPanel.add(checkbox10)

checkbox10.onChange(function(checked) {
  // Shows or hides the first map layer based on the checkbox's value. 
  Map.layers().get(9).setShown(checked); 
});

Map.addLayer(thal,{color: 'LightCoral'},'Thal',false);                                     

//------------------------------------------------------------------------------------------------------------------------------------------------------------


// set position for classification panel
var legend = ui.Panel({
  style: {
    position: 'bottom-right',
    padding: '8px 15px'
  }
});

// Create legend title
var legendTitle2 = ui.Label({
  value: 'Classification Legend',
  //style: {fontWeight: 'bold',fontSize: '18px',margin: '0 0 4px 0',padding: '0'}
  style: {fontWeight: 'bold'}
});

// Add the title to the panel
//legend.add(legendTitle);
    
// Creates and styles 1 row of the legend.
var makeRow = function(color, name) {
      
      // Create the label that is actually the colored box.
      var colorBox = ui.Label({
        style: {
          backgroundColor: '#' + color,
          // Use padding to give the box height and width.
          padding: '8px',
          margin: '0 0 4px 0'
        }
      });
      
      // Create the label filled with the description text.
      var description = ui.Label({
        value: name,
        style: {margin: '0 0 4px 6px'}
      });
      
      // return the panel
      return ui.Panel({
        widgets: [colorBox, description],
        layout: ui.Panel.Layout.Flow('horizontal')
      });
};


//  Palette with the colors
var palette =['FFFF00','FF0000','FFA500','F0E68C','FF69B4','00FF00','7FFFD4','FFD700','0000FF','F08080'];

// name of the legend
var names = ['Pygoscelis Adeliae','Aptenodytes forsteri','Daption capense', 'Fulmarus glacialoides','Macronectes Giganteus', 'Oceanites Oceanicus','Pagodroma Nivea', 'Phoebetria Palpebrata', 
'Stercorarius Maccormicki', 'Thalassoica Antarctica'];

// Add color and and names
for (var i = 0; i < 10; i++) {
  legend.add(makeRow(palette[i],names[i]));
  }

// add legend to map (alternatively you can also print the legend to the console)  
//Map.add(legend); 

//var legendPanel2 = ui.Panel([legendTitle2, makeRow]);
//inspectorPanel.widgets().set(3, legendPanel2);

inspectorPanel.add(legendTitle2).add(legend)
