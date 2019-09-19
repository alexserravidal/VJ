# Exercicis OpenGL
## Primitives
**Exercici 1. Encara que els rectangles (quads) que s'envien a pintar tenen la mateixa amplada i alçada es dibuixen com a rectangles.
Prova a canviar les coordenades dels vèrtexs per fer que els quads siguin quadrats.** 
> L'arxiu **main.cpp** pinta una pantalla de width 640px i height 480px a través de la funció _glutInitWindowSize(640,480)_, 
> fent que hi hagi una relació d'aspecte de _640/480 = 1.33_. Això vol dir que una unitat de llargada es veurà 1.33 cops més gran que
> una d'alçada. Per tant, podríem arreglar el problema multiplicant per 1.33 l'alçada en la funció que pinta els quads. 
>
> Aquesta funció, que es crida a l'arxiu **Scene.cpp** encarregat de pintar l'escena, es pot modificar de la següent forma per a què els
> quads siguin quadrats: 
>
>     void Scene::init()
>     {
>       initShaders();
>       for(int i = 0; i < 4; i++)
>         quads[i] = Quad::createQuad(-0.75f + (i % 2), -0.75f + (i / 2), 0.5f, 0.5f*1.33f, program);
>     }
