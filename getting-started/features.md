---
description: Verge3D工具包功能特性列表
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
      <td style="text-align:left">&#x52A8;&#x753B;</td>
      <td style="text-align:left">
        <p>Verge3D&#x652F;&#x6301;&#x4EE5;&#x4E0B;&#x7C7B;&#x578B;&#x7684;&#x52A8;&#x753B;&#xFF1A;</p>
        <ul>
          <li>&#x57FA;&#x4E8E;&#x9AA8;&#x9ABC;&#x9A71;&#x52A8;&#x7684;&#x52A8;&#x753B;</li>
          <li>&#x5BF9;&#x8C61;&#x53D8;&#x6362;&#x52A8;&#x753B;&#xFF0C;&#x5305;&#x62EC;&#x4F4D;&#x7F6E;&#xFF0C;&#x65CB;&#x8F6C;&#x548C;&#x7F29;&#x653E;&#x3002;</li>
          <li>&#x6750;&#x8D28;&#x53C2;&#x6570;&#x52A8;&#x753B;&#x3002;&#x652F;&#x6301;&#x6D6E;&#x70B9;&#x548C;&#x989C;&#x8272;&#x53C2;&#x6570;&#x3002;</li>
          <li>&#x76EE;&#x6807;&#x878D;&#x5408;&#x52A8;&#x753B;&#xFF08;Morph target animation&#xFF09;&#xFF0C;&#x53C8;&#x79F0;&#x4E4B;&#x5F62;&#x72B6;&#x5E27;&#x52A8;&#x753B;&#xFF08;&#x4EC5;&#x9650;&#x4E8E;Verge3D
            for Blender&#xFF09;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x53EF;&#x89C6;&#x5316;&#x7F16;&#x7A0B;</td>
      <td style="text-align:left">
        <p><a href="puzzles-visual-logic-editor.md">Verge3D&#x62FC;&#x56FE;&#x7CFB;&#x7EDF;&#xFF08;Verge3D Puzzles&#xFF09;</a>&#x662F;&#x4E00;&#x79CD;&#x53EF;&#x89C6;&#x5316;&#x903B;&#x8F91;&#x73AF;&#x5883;&#xFF0C;&#x5141;&#x8BB8;&#x4EE5;&#x62D6;&#x653E;&#x65B9;&#x5F0F;&#x5FEB;&#x901F;&#x521B;&#x5EFA;&#x4EA4;&#x4E92;&#x5F0F;&#x573A;&#x666F;&#xFF0C;&#x62E5;&#x6709;&#x4EE5;&#x4E0B;&#x6A21;&#x5757;&#xFF1A;</p>
        <ul>
          <li>&#x5904;&#x7406;&#x7528;&#x6237;&#x4E8B;&#x4EF6;&#xFF0C;&#x4F8B;&#x5982;&#x9F20;&#x6807;&#x70B9;&#x51FB;/&#x89E6;&#x6478;&#xFF0C;&#x60AC;&#x505C;&#x548C;&#x62D6;&#x52A8;&#xFF1B;</li>
          <li>&#x68C0;&#x7D22;&#x573A;&#x666F;&#x5BF9;&#x8C61;&#xFF0C;&#x52A8;&#x753B;&#xFF0C;&#x7EC4;&#x548C;&#x6750;&#x8D28;&#xFF1B;</li>
          <li>&#x79FB;&#x52A8;/&#x65CB;&#x8F6C;/&#x7F29;&#x653E;3D&#x5BF9;&#x8C61;&#xFF0C;&#x83B7;&#x5F97;&#x5BF9;&#x8C61;&#x4E4B;&#x95F4;&#x7684;&#x8DDD;&#x79BB;&#xFF1B;</li>
          <li>&#x663E;&#x793A;/&#x9690;&#x85CF;&#x5BF9;&#x8C61;&#xFF1B;</li>
          <li>&#x66F4;&#x6539;&#x5BF9;&#x8C61;&#x7684;&#x5C42;&#x6B21;&#x7ED3;&#x6784;&#xFF1B;</li>
          <li>&#x5C06;2D&#x6587;&#x672C;&#x6CE8;&#x91CA;&#xFF08;billboards&#xFF09;&#x6DFB;&#x52A0;&#x5230;&#x573A;&#x666F;&#x4E2D;&#xFF1B;</li>
          <li>&#x6539;&#x53D8;&#x6750;&#x8D28;&#x53C2;&#x6570;&#xFF0C;&#x52A0;&#x8F7D;&#x7EB9;&#x7406;&#xFF1B;</li>
          <li>&#x63A7;&#x5236;&#x52A8;&#x753B;&#xFF1B;</li>
          <li>&#x79FB;&#x52A8;&#xFF0C;&#x65CB;&#x8F6C;&#x76F8;&#x673A;&#xFF1B;</li>
          <li>&#x8BBE;&#x7F6E;&#x6709;&#x6E90;&#x6444;&#x50CF;&#x5934;&#xFF1B;</li>
          <li>&#x52A8;&#x6001;&#x52A0;&#x8F7D;&#x8D44;&#x4EA7;&#xFF1B;</li>
          <li>&#x901A;&#x8FC7;&#x7F51;&#x7EDC;&#x4EE5;JSON / CSV /&#x6587;&#x672C;&#x683C;&#x5F0F;&#x4E0A;&#x4F20;/&#x4E0B;&#x8F7D;&#x6570;&#x636E;&#xFF1B;</li>
          <li>&#x52A0;&#x8F7D;&#x7528;&#x6237;&#x56FE;&#x50CF;&#xFF1B;</li>
          <li>&#x5B9E;&#x73B0;&#x64A4;&#x6D88;/&#x91CD;&#x505A;&#x529F;&#x80FD;&#xFF1B;</li>
          <li>&#x586B;&#x5199;&#x548C;&#x53D1;&#x9001;&#x5BA2;&#x6237;&#x8BA2;&#x5355;&#xFF1B;</li>
          <li>&#x68C0;&#x6D4B;&#x7528;&#x6237;&#x529F;&#x80FD;&#xFF0C;&#x5982;&#x6D4F;&#x89C8;&#x5668;&#xFF0C;&#x64CD;&#x4F5C;&#x7CFB;&#x7EDF;&#x7B49;&#xFF1B;</li>
          <li>&#x4E0E;&#x7528;JavaScript&#x7F16;&#x5199;&#x7684;&#x903B;&#x8F91;&#x4E8B;&#x4EF6;&#x4EA4;&#x4E92;&#xFF1B;</li>
          <li>&#x6267;&#x884C;&#x57FA;&#x4E8E;&#x8BA1;&#x65F6;&#x5668;&#x7684;&#x4E8B;&#x4EF6;&#xFF1B;</li>
          <li>&#x521D;&#x59CB;&#x5316;&#x865A;&#x62DF;&#x73B0;&#x5B9E;&#x4F1A;&#x8BDD;&#x73AF;&#x5883;&#xFF1B;</li>
          <li>&#x7BA1;&#x7406;&#x5DF2;&#x52A0;&#x8F7D;&#x9875;&#x9762;&#x7684;HTML /
            CSS&#x5E03;&#x5C40;&#xFF1B;</li>
          <li>&#x64AD;&#x653E;&#x58F0;&#x97F3;&#xFF1B;</li>
          <li>&#x6A21;&#x62DF;&#x7269;&#x7406;&#x73AF;&#x5883;&#xFF1B;</li>
          <li>&#x542F;&#x7528;&#x540E;&#x671F;&#x7279;&#x6548;&#x5904;&#x7406;&#xFF1B;</li>
          <li>&#x7BA1;&#x7406;&#x5E94;&#x7528;&#x7A0B;&#x5E8F;&#x903B;&#x8F91;&#x548C;&#x6570;&#x636E;&#xFF1B;</li>
          <li>&#x6267;&#x884C;&#x6570;&#x5B66;&#x8FD0;&#x7B97;&#xFF1B;</li>
          <li>&#x2026;&#x2026;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x7F16;&#x7A0B;</td>
      <td style="text-align:left">
        <p>&#x53EF;&#x4EE5;<a href="../general-topics/using-javascript.md">&#x4F7F;&#x7528;JavaScript&#x4FEE;&#x6539;</a>&#x5E94;&#x7528;&#x7A0B;&#x5E8F;&#x6E90;&#x6587;&#x4EF6;&#x6216;&#x901A;&#x8FC7;&#x5728;Puzzles&#x4E2D;&#x96C6;&#x6210;&#x4EE3;&#x7801;&#x6765;&#x6DFB;&#x52A0;&#x5E94;&#x7528;&#x7A0B;&#x5E8F;&#x529F;&#x80FD;&#x3002;</p>
        <p>Verge3D&#x57FA;&#x4E8E;&#x5F00;&#x6E90;&#x5E93;Three.js&#xFF0C;&#x5E76;&#x901A;&#x8FC7;<b>v3d</b>&#x6216;<b>THREE</b>&#x547D;&#x540D;&#x7A7A;&#x95F4;&#x516C;&#x5F00;&#x5176;API&#x3002;&#x56E0;&#x6B64;&#xFF0C;Verge3D&#x4E2D;&#x53EF;&#x4EE5;&#x590D;&#x7528;&#x4EFB;&#x4F55;&#x73B0;&#x6709;&#x7684;Three.js&#x4EE3;&#x7801;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x53D1;&#x5E03;</td>
      <td style="text-align:left">
        <p>&#x60A8;&#x53EF;&#x4EE5;&#x901A;&#x8FC7;&#x4EE5;&#x4E0B;&#x65B9;&#x5F0F;&#x53D1;&#x5E03;&#x60A8;&#x7684;&#x521B;&#x4F5C;&#x5185;&#x5BB9;&#xFF1A;</p>
        <ul>
          <li>&#x81EA;&#x6709;&#x670D;&#x52A1;&#x5668;&#xFF1B;</li>
          <li>&#x4EFB;&#x610F;&#x7F51;&#x7EDC;&#x6258;&#x7BA1;&#x670D;&#x52A1;&#xFF08;&#x4E9A;&#x9A6C;&#x900A;AWS&#x3001;&#x963F;&#x91CC;&#x4E91;&#x3001;&#x817E;&#x8BAF;&#x4E91;&#x7B49;&#xFF09;&#xFF1B;</li>
          <li>Verge3D&#x4E91;&#x670D;&#x52A1;&#xFF08;Verge3D &#xFF09;&#xFF1B;</li>
          <li>Facebook&#xFF08;&#x4F7F;&#x7528;<a href="../general-topics/facebook-3d-posts.md">3D&#x4E3B;&#x9898;</a>&#x529F;&#x80FD;&#xFF09;&#xFF1B;</li>
          <li>&#x4F7F;&#x7528;Electron&#x6216;Cordova&#x6846;&#x67B6;&#x521B;&#x5EFA;&#x7684;&#x72EC;&#x7ACB;&#x684C;&#x9762;&#x6216;&#x79FB;&#x52A8;&#x5E94;&#x7528;&#x7A0B;&#x5E8F;&#x3002;</li>
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
      <td style="text-align:left">UI&#x4E0E;HTML&#x5E03;&#x5C40;</td>
      <td style="text-align:left">
        <p>&#x4F7F;&#x7528;&#x5916;&#x90E8;&#x6240;&#x89C1;&#x65E2;&#x6240;&#x5F97;&#x7F16;&#x8F91;&#x5668;&#xFF08;WYSIWYG
          editor&#xFF09;&#x521B;&#x5EFA;&#x7684;&#x754C;&#x9762;&#x5E03;&#x5C40;&#x53EF;&#x4EE5;
          <a
          href="../general-topics/html-based-user-interfaces.md">&#x4E0E;Puzzles&#x94FE;&#x63A5;</a>&#xFF0C;&#x4EE5;&#x89E6;&#x53D1;&#x5BF9;&#x5728;&#x6D4F;&#x89C8;&#x5668;&#x4E2D;&#x5448;&#x73B0;&#x7684;3D&#x573A;&#x666F;&#x7684;&#x66F4;&#x6539;&#xFF0C;&#x53CD;&#x4E4B;&#x4EA6;&#x7136;&#x3002;</p>
        <p>&#x4EE5;&#x4E0B;&#x7F51;&#x9875;&#x8BBE;&#x8BA1;&#x5DE5;&#x5177;&#x5DF2;&#x7ECF;&#x8FC7;&#x6D4B;&#x8BD5;&#x53EF;&#x7528;&#x4E8E;Verge3D&#x751F;&#x4EA7;&#x6D41;&#x7A0B;&#xFF1A;</p>
        <ul>
          <li>Webflow</li>
          <li>Google Web Designer</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x670D;&#x52A1;&#x5668;&#x7AEF;&#x529F;&#x80FD;</td>
      <td style="text-align:left">
        <p>Verge3D&#x9644;&#x5E26;&#x4E86;&#x4E00;&#x4E2A;<a href="../general-topics/wordpress-plugin.md">WordPress&#x63D2;&#x4EF6;</a>&#x3002;WordPress&#x662F;&#x76EE;&#x524D;&#x6700;&#x6D41;&#x884C;&#x7684;&#x5185;&#x5BB9;&#x7BA1;&#x7406;&#x7CFB;&#x7EDF;&#xFF08;CMS&#xFF09;&#x3002;&#x8BE5;&#x63D2;&#x4EF6;&#x5305;&#x62EC;&#x4EE5;&#x4E0B;&#x529F;&#x80FD;&#xFF1A;</p>
        <ul>
          <li>&#x5E94;&#x7528;&#x7A0B;&#x5E8F;&#x6258;&#x7BA1;&#x548C;&#x53D1;&#x5E03;&#xFF08;&#x5D4C;&#x5165;&#xFF09;</li>
          <li>&#x957F;&#x671F;&#x6587;&#x4EF6;&#x5B58;&#x50A8;</li>
          <li>&#x5B8C;&#x5168;&#x53EF;&#x5B9A;&#x5236;&#x7684;&#x7535;&#x5B50;&#x5546;&#x52A1;&#x7CFB;&#x7EDF;&#xFF0C;&#x7528;&#x4E8E;&#x5904;&#x7406;&#x5BA2;&#x6237;&#x8BA2;&#x5355;</li>
        </ul>
        <p>&#x9664;&#x6B64;&#x4E4B;&#x5916;&#xFF0C;Puzzles&#x53EF;&#x89C6;&#x5316;&#x903B;&#x8F91;&#x7F16;&#x8F91;&#x5668;&#x8FD8;&#x652F;&#x6301;&#x901A;&#x8FC7;&#x7F51;&#x7EDC;&#x4EE5;JSON&#xFF0C;CSV&#x6216;&#x7EAF;&#x6587;&#x672C;&#x683C;&#x5F0F;&#x53D1;&#x9001;/&#x68C0;&#x7D22;&#x6570;&#x636E;&#x7684;&#x6A21;&#x5757;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x540E;&#x671F;&#x7279;&#x6548;</td>
      <td style="text-align:left">
        <p>&#x62FC;&#x56FE;&#x7F16;&#x8F91;&#x5668;&#x4E2D;&#x53EF;&#x4EE5;&#x542F;&#x7528;&#x4EE5;&#x4E0B;&#x7279;&#x6548;&#xFF1A;</p>
        <ul>
          <li>&#x73AF;&#x5883;&#x5149;&#x906E;&#x853D;</li>
          <li>&#x6CDB;&#x5149;&#x6548;&#x679C;&#xFF08;Bloom&#xFF09;</li>
          <li>&#x4EAE;&#x5EA6;/&#x5BF9;&#x6BD4;&#x5EA6;</li>
          <li>&#x666F;&#x6DF1;</li>
          <li>&#x7070;&#x5EA6;</li>
        </ul>
        <p>&#x9664;&#x6B64;&#x4E4B;&#x5916;&#xFF0C;&#x53EF;&#x7528;JavaScript&#x542F;&#x7528;&#x4EE5;&#x4E0B;&#x6548;&#x679C;&#xFF1A;</p>
        <ul>
          <li>&#x81EA;&#x9002;&#x5E94;&#x8272;&#x8C03;&#x6620;&#x5C04;</li>
          <li>&#x4E91;&#x9699;&#x5149;&#xFF08;&#x4E5F;&#x79F0;&#x4E3A;&#x795E;&#x5149;&#x6216;&#x5723;&#x5149;&#x6548;&#x679C;&#xFF09;</li>
          <li>&#x589E;&#x5F3A;&#x7684;&#x4E9A;&#x50CF;&#x7D20;&#x5F62;&#x6001;&#x6297;&#x952F;&#x9F7F;&#xFF08;SMAA&#xFF09;</li>
          <li>&#x6BDB;&#x523A;</li>
          <li>&#x56FE;&#x50CF;&#x4EA4;&#x53C9;&#x6DE1;&#x5316;</li>
          <li>&#x56FE;&#x50CF;&#x906E;&#x7F69;/&#x63A9;&#x853D;&#xFF08;Image Mask&#xFF09;</li>
          <li>&#x8FD0;&#x52A8;&#x6A21;&#x7CCA;</li>
          <li>&#x50CF;&#x7D20;&#x5316;&#x56FE;&#x50CF;</li>
          <li>&#x7D22;&#x8D1D;&#x5C14;&#x8FC7;&#x6EE4;&#x5668;&#xFF08;Pixelated Imagery&#xFF09;</li>
          <li>&#x8D85;&#x7EA7;&#x91C7;&#x6837;&#x6297;&#x952F;&#x9F7F;&#xFF08;SSAA&#xFF09;</li>
          <li>&#x65F6;&#x95F4;&#x6027;&#x6297;&#x952F;&#x9F7F;&#xFF08;TAA&#xFF09;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x865A;&#x62DF;&#x73B0;&#x5B9E;</td>
      <td style="text-align:left"><a href="../general-topics/ar-vr-development.md">&#x652F;&#x6301;WebXR&#x548C;WebVR</a>&#xFF08;&#x901A;&#x8FC7;&#x517C;&#x5BB9;&#x6027;&#x652F;&#x6301;&#x6A21;&#x5757;&#xFF09;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x7740;&#x8272;&#x5668;</td>
      <td style="text-align:left">&#x53EF;&#x4EE5;&#x4F7F;&#x7528;OpenGL ES&#x7740;&#x8272;&#x8BED;&#x8A00;2.0&#xFF08;WebGL
        1.0&#xFF09;&#x6216;3.0&#xFF08;WebGL 2.0&#xFF09;&#x6DFB;&#x52A0;&#x81EA;&#x5B9A;&#x4E49;&#x7740;&#x8272;&#x5668;&#xFF08;Shaders&#xFF09;&#x3002;</td>
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