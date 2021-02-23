#Empty AOV Tool

#Creating variables here
_selected_nodes = nuke.selectedNodes()
_curve_tool = nuke.createNode('CurveTool')

node = nuke.selectedNode()
_original_aovs = [node.channels()]

#Connecting inputs to the newly created curve tool
nuke.nodes.CurveTool(inputs =_selected_nodes)

# This part swithches the channels inside the curve toolm this will have to
# be assigned from a  list populated from the aov from the file
_curve_tool["channels"].setValue("id_2")

#Executing the curve tool here
nuke.execute(_curve_tool, nuke.frame(), nuke.frame())

#Outputing the restulting to  intensitydata
_intensitydata = _curve_tool['intensitydata'].value()

#Deleting the curve tool node
nuke.delete(_curve_tool)

#showing message with average data 
nuke.message('average luminance is %s' % _intensitydata)

print "extracted aovs" + str(_original_aovs)
print "DONE"
