Analyse fbx file and translate to to Mydefined and common data,Mesh/Material Supported

#include "loadFbxC.h"
void Import(const std::string &fbxPath)
{
            	FbxIOSetting ios;
           	 ios.ConvertToAxis = 2;
            	ios.ConvertToUnit = 2;
            	ios.progress = progressFunction;
		void* _scene=0;
            	loadFbxMemory(fbxPath, _scene, &ios);

            	MeshIO::FbxFullData* fulldata = (MeshIO::FbxFullData*)(_scene);
            	if (!fulldata || fulldata->meshs.count < 1)return;
            	MeshIO::MeshVector meshs = fulldata->meshs;
            
           	//TODO...

           	freeFbxMemory(_scene);
}
