---
description: Verge3D工具包的特性与功能列表
---

# 功能特性

编译中 - m@funjoy

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x529F;&#x80FD;</th>
      <th style="text-align:left">&#x7279;&#x6027;&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x521B;&#x5EFA;&#x5185;&#x5BB9;</td>
      <td style="text-align:left">
        <p>Verge3D&#x8D44;&#x4EA7;&#x53EF;&#x901A;&#x8FC7;&#x4EE5;&#x4E0B;&#x5DE5;&#x5177;&#x521B;&#x5EFA;&#xFF1A;</p>
        <ul>
          <li>Autodesk 3ds Max 2017-2020&#x7248;&#x672C;&#xFF0C;&#x5B89;&#x88C5;Verge3D
            for 3ds Max&#x63D2;&#x4EF6;&#x3002;</li>
          <li>Blender 2.79 &#x53CA; 2.80&#x7248;&#xFF0C;&#x5B89;&#x88C5;Verge3D for
            Blender&#x63D2;&#x4EF6;</li>
          <li>&#x4EFB;&#x4F55;&#x652F;&#x6301;&#x5BFC;&#x51FA;glTF2.0&#x683C;&#x5F0F;&#x6570;&#x636E;&#x7684;&#x4E09;&#x7EF4;&#x5EFA;&#x6A21;&#x5DE5;&#x5177;&#x3002;</li>
        </ul>
        <p>&#x5BFC;&#x51FA;&#x7684;&#x6587;&#x4EF6;&#x4EA6;&#x53EF;&#x538B;&#x7F29;&#x4E3A;LZMA
          / XZ&#x683C;&#x5F0F;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x6750;&#x8D28;&#x7CFB;&#x7EDF;</td>
      <td style="text-align:left">
        <p></p>
        <p>Verge3D for 3ds Max&#x652F;&#x6301;&#x7684;&#x6750;&#x8D28;&#xFF1A;</p>
        <ul>
          <li><a href="../3ds-max-artists-guide/material-systems.md#wu-li-cai-zhi-physical-materials">&#x7269;&#x7406;&#x6750;&#x8D28;</a> &#xFF0C;&#x53C2;&#x8003;ART&#x6E32;&#x67D3;&#x5668;&#x652F;&#x6301;&#x5217;&#x8868;&#x3002;</li>
          <li><a href="../3ds-max-artists-guide/material-systems.md#biao-zhun-cai-liao-standard-materials">&#x6807;&#x51C6;&#x6750;&#x8D28;</a> &#xFF0C;&#x53C2;&#x8003;&#x626B;&#x63CF;&#x7EBF;&#x6E32;&#x67D3;&#x5668;&#x652F;&#x6301;&#x91CC;&#x8BF6;&#x535A;&#x9CCC;</li>
          <li><a href="../3ds-max-artists-guide/material-systems.md#gltf-jian-rong-cai-liao-gltfcompliant-materials">glTF&#x517C;&#x5BB9;&#x7269;&#x7406;&#x6750;&#x8D28;</a>&#x3002;</li>
        </ul>
        <p>Verge3D for Blender&#x652F;&#x6301;&#x7684;&#x6750;&#x8D28;&#xFF1A;</p>
        <ul>
          <li><a href="../blender-artists-guide/material-system-overview.md#eevee-materials">Eevee</a> &#xFF08;&#x4EC5;&#x9650;Blender
            2.8&#xFF09;&#x3002;</li>
          <li><a href="../blender-artists-guide/material-system-overview.md#zhou-qi-cai-liao">Cycles</a> &#xFF08;Blender2.7&#x4E0E;2.8&#x5747;&#x53EF;&#xFF09;&#x3002;</li>
          <li><a href="../blender-artists-guide/material-system-overview.md#fu-he-gltf-biao-zhun-de-pbr-cai-liao">glTF-compliant PBR</a> &#x7B26;&#x5408;glTF&#x6807;&#x51C6;&#x7684;PBR&#x6750;&#x8D28;&#xFF08;Blender2.7&#x4E0E;2.8&#x5747;&#x53EF;&#xFF09;&#x3002;</li>
          <li>&#x6807;&#x51C6;&#x5185;&#x90E8;&#x6750;&#x8D28;&#xFF08;&#x4EC5;&#x9650;Blender
            2.7&#xFF0C;&#x5DF2;&#x5F03;&#x7528;&#xFF09;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Lights and Shadows</td>
      <td style="text-align:left">
        <p>Verge3D supports the following light types:</p>
        <ul>
          <li>Directional Light</li>
          <li>Point Light</li>
          <li>Spot Light</li>
          <li>Image-based Light - emitted from LDR and HDR maps.</li>
          <li>Procedural Light - emitted from customized environment material.</li>
          <li>Hemisphere Light - Verge3D for Blender only.</li>
          <li>Rectangular Area Light - can be created with JavaScript.</li>
        </ul>
        <p>Verge3D supports casting shadows from directional, point and spot light
          sources:</p>
        <ul>
          <li>Basic non-smoothed shadows</li>
          <li>PCF shadows</li>
          <li>Smoothed PCF shadows</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x706F;&#x5149;&#x4E0E;&#x9634;&#x5F71;</td>
      <td style="text-align:left">
        <p>Verge3D&#x652F;&#x6301;&#x4EE5;&#x4E0B;&#x706F;&#x5149;&#x7C7B;&#x578B;&#xFF1A;</p>
        <ul>
          <li>&#x5E73;&#x884C;&#x5149;</li>
          <li>&#x70B9;&#x5149;&#x6E90;</li>
          <li>&#x805A;&#x5149;&#x706F;</li>
          <li>&#x57FA;&#x4E8E;&#x56FE;&#x50CF;&#x7684;&#x5149;&#x6E90;&#x2014;&#x2014;&#x4ECE;LDR&#x548C;HDR&#x8D34;&#x56FE;&#x53D1;&#x5C04;</li>
          <li>&#x7A0B;&#x5E8F;&#x5149;&#x2014;&#x2014;&#x4ECE;&#x81EA;&#x5B9A;&#x4E49;&#x7684;&#x73AF;&#x5883;&#x8D34;&#x56FE;&#x53D1;&#x5C04;</li>
          <li>&#x534A;&#x7403;&#x5149;&#x6E90;&#x2014;&#x2014;&#x4EC5;&#x9650;Verge3D
            for Blender</li>
          <li>&#x77E9;&#x5F62;&#x9762;&#x5149;&#x6E90;-&#x53EF;&#x7528;Javascript&#x521B;&#x5EFA;</li>
        </ul>
        <p>Verge3D&#x652F;&#x6301;&#x4ECE;&#x5E73;&#x884C;&#x5149;&#x3001;&#x70B9;&#x5149;&#x6E90;&#x548C;&#x805A;&#x5149;&#x706F;&#x6295;&#x5C04;&#x9634;&#x5F71;&#xFF1A;</p>
        <p>Verge3D supports casting shadows from directional, point and spot light
          sources:</p>
        <ul>
          <li>&#x57FA;&#x672C;&#x975E;&#x5E73;&#x6ED1;&#x9634;&#x5F71;</li>
          <li>PCF&#x9634;&#x5F71;</li>
          <li>&#x5E73;&#x6ED1;PCF&#x9634;&#x5F71;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5E94;&#x7528;&#x7BA1;&#x7406;</td>
      <td style="text-align:left">
        <p></p>
        <p>&#x5E94;&#x7528;&#x7BA1;&#x7406;&#x5668;&#xFF08;App Manager&#xFF09;&#x662F;&#x4E00;&#x4E2A;&#x8F7B;&#x91CF;&#x5316;&#x7684;&#x7BA1;&#x7406;&#x5DE5;&#x5177;&#xFF1A;</p>
        <ul>
          <li>&#x57FA;&#x4E8E;&#x6A21;&#x677F;&#x521B;&#x5EFA;&#x65B0;&#x5E94;&#x7528;</li>
          <li>&#x542F;&#x52A8;3d&#x5EFA;&#x6A21;&#x5957;&#x4EF6;&#xFF08;Blender, 3ds
            Max&#xFF09;</li>
          <li>&#x7F16;&#x8F91;&#x4E0E;&#x8FD0;&#x884C;&#x62FC;&#x56FE;&#x903B;&#x8F91;&#xFF08;Puzzles
            logic&#xFF09;</li>
          <li>&#x66F4;&#x65B0;&#x5E94;&#x7528;&#x81F3;Verge3D&#x6700;&#x65B0;&#x7248;</li>
          <li>&#x5728;Verge3D&#x4E91;&#x670D;&#x52A1;&#xFF08;Verge3D Network&#xFF09;&#x4E2D;&#x53D1;&#x5E03;&#x5E94;&#x7528;</li>
          <li>&#x7BA1;&#x7406;&#x6388;&#x6743;&#x7801;</li>
          <li>&#x8BBF;&#x95EE;Verge3D&#x6587;&#x6863;&#x53CA;&#x652F;&#x6301;&#x6E20;&#x9053;</li>
        </ul>
        <p>&#x5E94;&#x7528;&#x7BA1;&#x7406;&#x5668;&#xFF08;App Manager&#xFF09;&#x53EF;&#x4EE5;&#x4ECE;Blender&#x4E0E;3ds
          Max&#x4E2D;&#x76F4;&#x63A5;&#x6253;&#x5F00;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Animation</td>
      <td style="text-align:left">
        <p>Verge3D supports the following types of animation:</p>
        <ul>
          <li>Skeletal armature-based animation.</li>
          <li>Object transform animation, including position, rotation and scale.</li>
          <li>Material params animation. Supported float and color parameters.</li>
          <li>Morph target animation, also known as shape keys (Verge3D for Blender
            only).</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x52A8;&#x753B;</td>
      <td style="text-align:left">Verge3D&#x652F;&#x6301;&#x4EE5;&#x4E0B;&#x7C7B;&#x578B;&#x7684;&#x52A8;&#x753B;&#xFF1A;</td>
    </tr>
    <tr>
      <td style="text-align:left">Visual Programming</td>
      <td style="text-align:left">
        <p><a href="http://soft8soft.com/docs/manual/en/introduction/Puzzles-Visual-Logic-Editor.html">Verge3D Puzzles</a> is
          a visual logic environment which allows for quick creation of interactive
          scenarios in a drag-and-drop fashion. It features blocks for:</p>
        <ul>
          <li>Handing user events, such as mouse clicks/touches, hovering and dragging.</li>
          <li>Retrieving scene objects, animations, groups and materials.</li>
          <li>Moving/rotating/scaling 3D objects, getting distance between objects.</li>
          <li>Showing/hiding objects.</li>
          <li>Changing objects&apos; hierarchy.</li>
          <li>Adding 2D textual annotations (billboards) to the scene.</li>
          <li>Changing material params, loading textures.</li>
          <li>Controlling animations.</li>
          <li>Moving, rotating cameras. Setting the active camera.</li>
          <li>Dynamically loading assets.</li>
          <li>Uploading/downloading data over network in JSON/CSV/Text format.</li>
          <li>Loading user images.</li>
          <li>Implementing Undo/Redo feature.</li>
          <li>Composing and sending customer orders.</li>
          <li>Detecting user capabilities such as browser, OS etc.</li>
          <li>Interacting with logic written in JavaScript.</li>
          <li>Executing timer-based events.</li>
          <li>Initializing Virtual Reality sessions.</li>
          <li>Managing HTML/CSS layouts of the loaded page.</li>
          <li>Playing sounds.</li>
          <li>Simulating physics environments.</li>
          <li>Enabling post-processing effects.</li>
          <li>Managing app logic and data.</li>
          <li>Doing math.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Programming</td>
      <td style="text-align:left">
        <p>Application functionality can be <a href="http://soft8soft.com/docs/manual/en/introduction/Using-JavaScript.html">added via JavaScript</a> by
          modifying application sources or by integrating code in Puzzles.</p>
        <p>Verge3D is based on open-source library Three.js and exposes its API via <b>v3d</b> or <b>THREE</b> namespace.
          Therefore, it is possible to reuse any existing Three.js code with Verge3D.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Publishing</td>
      <td style="text-align:left">
        <p>You can distribute your content using:</p>
        <ul>
          <li>You own server.</li>
          <li>Any web hosting service (GoDaddy, DigitalOcean, Amazon AWS etc).</li>
          <li>Verge3D Network.</li>
          <li>Facebook (by using the <a href="http://soft8soft.com/docs/manual/en/introduction/Facebook-3D-Posts.html">3D posts</a> feature).</li>
          <li>As stand-alone desktop or mobile application created with Electron or
            Cordova frameworks.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">UI and HTML Layout</td>
      <td style="text-align:left">
        <p>Interface layouts, created using external WYSIWYG editors, can be <a href="http://soft8soft.com/docs/manual/en/introduction/HTML-based-user-interfaces.html">linked with Puzzles</a> to
          trigger changes to a 3D scene being rendered in the browser and vice versa.</p>
        <p>The following website builders are tested and known to work:</p>
        <ul>
          <li>Webflow</li>
          <li>Google Web Designer</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Server-Side Features</td>
      <td style="text-align:left">
        <p>Verge3D comes with a <a href="http://soft8soft.com/docs/manual/en/introduction/Wordpress-Plugin.html">plug-in for WordPress</a>,
          the most popular content management system (CMS) in use. The plug-in includes
          the following features:</p>
        <ul>
          <li>Application hosting and publishing (embedding).</li>
          <li>Persistent file storage.</li>
          <li>Fully customizable e-commerce system for processing customer orders.</li>
        </ul>
        <p>In addition to that, the Puzzles visual logic editor supports blocks for
          sending/retrieving data over network in JSON, CSV or plain text format.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Post-processing effects</td>
      <td style="text-align:left">
        <p>The following effects can be enabled with Puzzles:</p>
        <ul>
          <li>Ambient Occlusion</li>
          <li>Bloom</li>
          <li>Brightness/Contrast</li>
          <li>Depth of Field</li>
          <li>Grayscale</li>
        </ul>
        <p>In addition, the following effects can be enabled with JavaScript:</p>
        <ul>
          <li>Adaptive Tone Mapping</li>
          <li>Crepuscular Rays (also known as sunbeams or god rays)</li>
          <li>Enhanced Subpixel Morphological Anti-Aliasing (SMAA)</li>
          <li>Glitch</li>
          <li>Image Crossfading</li>
          <li>Image Masking</li>
          <li>Motion Blur</li>
          <li>Pixelated Imagery</li>
          <li>Sobel Filter</li>
          <li>Supersampling Anti-Aliasing (SSAA)</li>
          <li>Temporal Anti-Aliasing (TAA)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Virtual Reality</td>
      <td style="text-align:left">Both WebXR and WebVR (via compatibility support module) are <a href="http://soft8soft.com/docs/manual/en/introduction/AR-VR-development.html">supported</a>.</td>
    </tr>
    <tr>
      <td style="text-align:left">Shaders</td>
      <td style="text-align:left">Custom shaders can be added using OpenGL ES Shading Language 2.0 (WebGL
        1.0) or 3.0 (WebGL 2.0).</td>
    </tr>
    <tr>
      <td style="text-align:left">Physics</td>
      <td style="text-align:left">The physics module enables for collision detection, dynamically moving
        objects, support for characters and vehicles, springs, ropes and cloth
        simulation. As of version 2.11, physics simulations can be created and
        controlled without coding via Puzzles.</td>
    </tr>
    <tr>
      <td style="text-align:left">Audio</td>
      <td style="text-align:left">Background music and/or event sounds can be added with Sound Puzzles to
        be triggered by the user.</td>
    </tr>
    <tr>
      <td style="text-align:left">Demos and Examples</td>
      <td style="text-align:left">
        <p>Over 150 coding examples and a series of fully-featured 3D apps including:</p>
        <ul>
          <li>City - large urban environment with first-person controls and ground detection.</li>
          <li>Custom Image - a virtual picture frame which allows uploading, storing
            and sharing your images.</li>
          <li>Farmer&apos;s Journey - arcade browser game made without coding.</li>
          <li>Industrial Robot VR - interactive robot simulator with VR capabilities.</li>
          <li>Recliner - 3D configruator and ready-to-use e-commerce website.</li>
          <li>Ring - simple 3D jewelry customizer with online ordering capabilities.</li>
          <li>Scooter - advanced 3D configurator with realistic PBR materials and millions
            possible combinations.</li>
          <li>Teapot Heater - non-trivial interactive 3D animation made with Puzzles.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Import Formats</td>
      <td style="text-align:left">
        <p>In addition to glTF 2.0 you can import the following formats.</p>
        <p>Geometry/Materials:</p>
        <ul>
          <li>3DS - older Autodesk 3ds Max file format</li>
          <li>3MF - 3D manufacturing format</li>
          <li>AMF - Additive manufacturing file format</li>
          <li>AWD - used in Away3D engine</li>
          <li>babylon - used in Babylon.js engine</li>
          <li>COLLADA</li>
          <li>CTM - OpenCTM format</li>
          <li>FBX</li>
          <li>glTF 1.0 - legacy format, use glTF 2.0 instead</li>
          <li>KMZ - Keyhole Markup Language</li>
          <li>OBJ/MTL</li>
          <li>PCD - 3D point cloud data format</li>
          <li>PDB - Protein Data Bank format</li>
          <li>PlayCanvas - JSON-based data format used in PlayCanvas engine</li>
          <li>PLY - Polygon File Format, designed to store three-dimensional data from
            3D scanners</li>
          <li>PRWM - Packed Raw WebGL Model</li>
          <li>STL - stereolithography data format, takes its origin from the CAD software
            by 3D Systems</li>
          <li>SEA3D - an open-source format for game development</li>
          <li>VRML - Virtual Reality Modeling Language</li>
          <li>VRM - glTF-based 3D avatar format</li>
          <li>VTK - Visualization Toolkit format</li>
          <li>X - DirectX file format</li>
        </ul>
        <p>Animation:</p>
        <ul>
          <li>BVH - Biovision Hierarchy character animation file format</li>
          <li>MD2 - used in Quake II engine</li>
          <li>MMD - MikuMikuDance format</li>
        </ul>
        <p>Images:</p>
        <ul>
          <li>DDS - texture compression format</li>
          <li>EXR - OpenEXR, high dynamic range raster file format</li>
          <li>PVR - texture compression format</li>
          <li>HDR - RGBE or Radiance HDR</li>
          <li>KTX - texture format by Khronos</li>
          <li>NRRD - &quot;nearly raw raster data&quot; format</li>
          <li>SVG</li>
          <li>TGA - Truevision TGA raster graphics format</li>
          <li>TTF</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Export Formats</td>
      <td style="text-align:left">
        <p>In addition to glTF 2.0 you can export to the following formats:</p>
        <ul>
          <li>COLLADA</li>
          <li>MMD</li>
          <li>OBJ</li>
          <li>PLY</li>
          <li>STL</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Camera Controls</td>
      <td style="text-align:left">
        <p>These camera control modes are available out-of-the-box:</p>
        <ul>
          <li>Orbit Controls - targeted 3D view</li>
          <li>Flying Controls - free-flight view</li>
          <li>First-Person Controls</li>
          <li>Virtual Reality Controls</li>
        </ul>
        <p>These camera control modes can be enabled with JavaScript:</p>
        <ul>
          <li>Flyover Controls</li>
          <li>Pointerlock Controls</li>
          <li>Device Orientation Controls - implements gyroscope-driven view</li>
          <li>Map Controls - hovering camera</li>
          <li>Trackball Controls</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">3D Primitives</td>
      <td style="text-align:left">
        <p>You can load geometry exported from any modelling suite. In addition to
          that, the following 3D primitives can be created with JavaScript:</p>
        <ul>
          <li>Cone</li>
          <li>Convex Hull</li>
          <li>Cube (Box)</li>
          <li>Cylinder</li>
          <li>Dodecahedron - a polyhedron with twelve flat faces</li>
          <li>Extruded Shape</li>
          <li>Icosahedron - a polyhedron with 20 faces</li>
          <li>NURBS</li>
          <li>Octahedron - a polyhedron with eight faces</li>
          <li>Plane</li>
          <li>Ring</li>
          <li>Sphere</li>
          <li>Tetrahedron - a triangular pyramid</li>
          <li>Polyhedron</li>
          <li>Spline Curve</li>
          <li>Text</li>
          <li>Torus</li>
          <li>Tube</li>
          <li>Utah Teapot</li>
          <li>Wireframe</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>