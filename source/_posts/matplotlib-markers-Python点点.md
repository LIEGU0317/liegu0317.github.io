---
title: matplotlib.markers|Python点点
tags:
  - matplotlib
  - Python
categories:
  - 经验
  - Python点点
index_img: 'https://github.com/LIEGU0317/img/raw/master/Blogimg/202112222052316.png'
hide: false
description:  Functions to handle markers; used by the marker functionality of plot, scatter, and errorbar.All possible markers are defined here
comment: twikoo
date: 2022-02-17 09:09:02
---

*全文摘自：[matplotlib.markers](https://matplotlib.org/stable/api/markers_api.html)*
<div>
<section id="module-matplotlib.markers">
<span id="matplotlib-markers"></span><h1><code class="docutils literal notranslate"><span class="pre">matplotlib.markers</span></code><a class="headerlink" href="#module-matplotlib.markers" title="Permalink to this headline">¶</a></h1>
<p>Functions to handle markers; used by the marker functionality of
<a class="reference internal" href="_as_gen/matplotlib.axes.Axes.plot.html#matplotlib.axes.Axes.plot" title="matplotlib.axes.Axes.plot"><code class="xref py py-obj docutils literal notranslate"><span class="pre">plot</span></code></a>, <a class="reference internal" href="_as_gen/matplotlib.axes.Axes.scatter.html#matplotlib.axes.Axes.scatter" title="matplotlib.axes.Axes.scatter"><code class="xref py py-obj docutils literal notranslate"><span class="pre">scatter</span></code></a>, and
<a class="reference internal" href="_as_gen/matplotlib.axes.Axes.errorbar.html#matplotlib.axes.Axes.errorbar" title="matplotlib.axes.Axes.errorbar"><code class="xref py py-obj docutils literal notranslate"><span class="pre">errorbar</span></code></a>.</p>
<p>All possible markers are defined here:</p>
<table class="table">
<colgroup>
<col style="width: 39%">
<col style="width: 8%">
<col style="width: 53%">
</colgroup>
<thead>
<tr class="row-odd"><th class="head"><p>marker</p></th>
<th class="head"><p>symbol</p></th>
<th class="head"><p>description</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"."</span></code></p></td>
<td><p><img alt="m00" src="https://matplotlib.org/stable/_images/m00.png"></p></td>
<td><p>point</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">","</span></code></p></td>
<td><p><img alt="m01" src="https://matplotlib.org/stable/_images/m01.png"></p></td>
<td><p>pixel</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"o"</span></code></p></td>
<td><p><img alt="m02" src="https://matplotlib.org/stable/_images/m02.png"></p></td>
<td><p>circle</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"v"</span></code></p></td>
<td><p><img alt="m03" src="https://matplotlib.org/stable/_images/m03.png"></p></td>
<td><p>triangle_down</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"^"</span></code></p></td>
<td><p><img alt="m04" src="https://matplotlib.org/stable/_images/m04.png"></p></td>
<td><p>triangle_up</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"&lt;"</span></code></p></td>
<td><p><img alt="m05" src="https://matplotlib.org/stable/_images/m05.png"></p></td>
<td><p>triangle_left</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"&gt;"</span></code></p></td>
<td><p><img alt="m06" src="https://matplotlib.org/stable/_images/m06.png"></p></td>
<td><p>triangle_right</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"1"</span></code></p></td>
<td><p><img alt="m07" src="https://matplotlib.org/stable/_images/m07.png"></p></td>
<td><p>tri_down</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"2"</span></code></p></td>
<td><p><img alt="m08" src="https://matplotlib.org/stable/_images/m08.png"></p></td>
<td><p>tri_up</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"3"</span></code></p></td>
<td><p><img alt="m09" src="https://matplotlib.org/stable/_images/m09.png"></p></td>
<td><p>tri_left</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"4"</span></code></p></td>
<td><p><img alt="m10" src="https://matplotlib.org/stable/_images/m10.png"></p></td>
<td><p>tri_right</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"8"</span></code></p></td>
<td><p><img alt="m11" src="https://matplotlib.org/stable/_images/m11.png"></p></td>
<td><p>octagon</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"s"</span></code></p></td>
<td><p><img alt="m12" src="https://matplotlib.org/stable/_images/m12.png"></p></td>
<td><p>square</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"p"</span></code></p></td>
<td><p><img alt="m13" src="https://matplotlib.org/stable/_images/m13.png"></p></td>
<td><p>pentagon</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"P"</span></code></p></td>
<td><p><img alt="m23" src="https://matplotlib.org/stable/_images/m23.png"></p></td>
<td><p>plus (filled)</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"*"</span></code></p></td>
<td><p><img alt="m14" src="https://matplotlib.org/stable/_images/m14.png"></p></td>
<td><p>star</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"h"</span></code></p></td>
<td><p><img alt="m15" src="https://matplotlib.org/stable/_images/m15.png"></p></td>
<td><p>hexagon1</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"H"</span></code></p></td>
<td><p><img alt="m16" src="https://matplotlib.org/stable/_images/m16.png"></p></td>
<td><p>hexagon2</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"+"</span></code></p></td>
<td><p><img alt="m17" src="https://matplotlib.org/stable/_images/m17.png"></p></td>
<td><p>plus</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"x"</span></code></p></td>
<td><p><img alt="m18" src="https://matplotlib.org/stable/_images/m18.png"></p></td>
<td><p>x</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"X"</span></code></p></td>
<td><p><img alt="m24" src="https://matplotlib.org/stable/_images/m24.png"></p></td>
<td><p>x (filled)</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"D"</span></code></p></td>
<td><p><img alt="m19" src="https://matplotlib.org/stable/_images/m19.png"></p></td>
<td><p>diamond</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"d"</span></code></p></td>
<td><p><img alt="m20" src="https://matplotlib.org/stable/_images/m20.png"></p></td>
<td><p>thin_diamond</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"|"</span></code></p></td>
<td><p><img alt="m21" src="https://matplotlib.org/stable/_images/m21.png"></p></td>
<td><p>vline</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">"_"</span></code></p></td>
<td><p><img alt="m22" src="https://matplotlib.org/stable/_images/m22.png"></p></td>
<td><p>hline</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">0</span></code> (<code class="docutils literal notranslate"><span class="pre">TICKLEFT</span></code>)</p></td>
<td><p><img alt="m25" src="https://matplotlib.org/stable/_images/m25.png"></p></td>
<td><p>tickleft</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">1</span></code> (<code class="docutils literal notranslate"><span class="pre">TICKRIGHT</span></code>)</p></td>
<td><p><img alt="m26" src="https://matplotlib.org/stable/_images/m26.png"></p></td>
<td><p>tickright</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">2</span></code> (<code class="docutils literal notranslate"><span class="pre">TICKUP</span></code>)</p></td>
<td><p><img alt="m27" src="https://matplotlib.org/stable/_images/m27.png"></p></td>
<td><p>tickup</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">3</span></code> (<code class="docutils literal notranslate"><span class="pre">TICKDOWN</span></code>)</p></td>
<td><p><img alt="m28" src="https://matplotlib.org/stable/_images/m28.png"></p></td>
<td><p>tickdown</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">4</span></code> (<code class="docutils literal notranslate"><span class="pre">CARETLEFT</span></code>)</p></td>
<td><p><img alt="m29" src="https://matplotlib.org/stable/_images/m29.png"></p></td>
<td><p>caretleft</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">5</span></code> (<code class="docutils literal notranslate"><span class="pre">CARETRIGHT</span></code>)</p></td>
<td><p><img alt="m30" src="https://matplotlib.org/stable/_images/m30.png"></p></td>
<td><p>caretright</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">6</span></code> (<code class="docutils literal notranslate"><span class="pre">CARETUP</span></code>)</p></td>
<td><p><img alt="m31" src="https://matplotlib.org/stable/_images/m31.png"></p></td>
<td><p>caretup</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">7</span></code> (<code class="docutils literal notranslate"><span class="pre">CARETDOWN</span></code>)</p></td>
<td><p><img alt="m32" src="https://matplotlib.org/stable/_images/m32.png"></p></td>
<td><p>caretdown</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">8</span></code> (<code class="docutils literal notranslate"><span class="pre">CARETLEFTBASE</span></code>)</p></td>
<td><p><img alt="m33" src="https://matplotlib.org/stable/_images/m33.png"></p></td>
<td><p>caretleft (centered at base)</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">9</span></code> (<code class="docutils literal notranslate"><span class="pre">CARETRIGHTBASE</span></code>)</p></td>
<td><p><img alt="m34" src="https://matplotlib.org/stable/_images/m34.png"></p></td>
<td><p>caretright (centered at base)</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">10</span></code> (<code class="docutils literal notranslate"><span class="pre">CARETUPBASE</span></code>)</p></td>
<td><p><img alt="m35" src="https://matplotlib.org/stable/_images/m35.png"></p></td>
<td><p>caretup (centered at base)</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">11</span></code> (<code class="docutils literal notranslate"><span class="pre">CARETDOWNBASE</span></code>)</p></td>
<td><p><img alt="m36" src="https://matplotlib.org/stable/_images/m36.png"></p></td>
<td><p>caretdown (centered at base)</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">"None"</span></code>, <code class="docutils literal notranslate"><span class="pre">"</span> <span class="pre">"</span></code> or <code class="docutils literal notranslate"><span class="pre">""</span></code></p></td>
<td></td>
<td><p>nothing</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">'$...$'</span></code></p></td>
<td><p><img alt="m37" src="https://matplotlib.org/stable/_images/m37.png"></p></td>
<td><p>Render the string using mathtext.
E.g <code class="docutils literal notranslate"><span class="pre">"$f$"</span></code> for marker showing the
letter <code class="docutils literal notranslate"><span class="pre">f</span></code>.</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">verts</span></code></p></td>
<td></td>
<td><p>A list of (x, y) pairs used for Path
vertices. The center of the marker is
located at (0, 0) and the size is
normalized, such that the created path
is encapsulated inside the unit cell.</p></td>
</tr>
<tr class="row-even"><td><p>path</p></td>
<td></td>
<td><p>A <a class="reference internal" href="path_api.html#matplotlib.path.Path" title="matplotlib.path.Path"><code class="xref py py-obj docutils literal notranslate"><span class="pre">Path</span></code></a> instance.</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">(numsides,</span> <span class="pre">0,</span> <span class="pre">angle)</span></code></p></td>
<td></td>
<td><p>A regular polygon with <code class="docutils literal notranslate"><span class="pre">numsides</span></code>
sides, rotated by <code class="docutils literal notranslate"><span class="pre">angle</span></code>.</p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">(numsides,</span> <span class="pre">1,</span> <span class="pre">angle)</span></code></p></td>
<td></td>
<td><p>A star-like symbol with <code class="docutils literal notranslate"><span class="pre">numsides</span></code>
sides, rotated by <code class="docutils literal notranslate"><span class="pre">angle</span></code>.</p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">(numsides,</span> <span class="pre">2,</span> <span class="pre">angle)</span></code></p></td>
<td></td>
<td><p>An asterisk with <code class="docutils literal notranslate"><span class="pre">numsides</span></code> sides,
rotated by <code class="docutils literal notranslate"><span class="pre">angle</span></code>.</p></td>
</tr>
</tbody>
</table>
<p><code class="docutils literal notranslate"><span class="pre">None</span></code> is the default which means 'nothing', however this table is
referred to from other docs for the valid inputs from marker inputs and in
those cases <code class="docutils literal notranslate"><span class="pre">None</span></code> still means 'default'.</p>
<p>Note that special symbols can be defined via the
<a class="reference internal" href="../tutorials/text/mathtext.html"><span class="doc">STIX math font</span></a>,
e.g. <code class="docutils literal notranslate"><span class="pre">"$\u266B$"</span></code>. For an overview over the STIX font symbols refer to the
<a class="reference external" href="http://www.stixfonts.org/allGlyphs.html">STIX font table</a>.
Also see the <a class="reference internal" href="../gallery/text_labels_and_annotations/stix_fonts_demo.html"><span class="doc">STIX Fonts</span></a>.</p>
<p>Integer numbers from <code class="docutils literal notranslate"><span class="pre">0</span></code> to <code class="docutils literal notranslate"><span class="pre">11</span></code> create lines and triangles. Those are
equally accessible via capitalized variables, like <code class="docutils literal notranslate"><span class="pre">CARETDOWNBASE</span></code>.
Hence the following are equivalent:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">([</span><span class="mi">1</span><span class="p">,</span> <span class="mi">2</span><span class="p">,</span> <span class="mi">3</span><span class="p">],</span> <span class="n">marker</span><span class="o">=</span><span class="mi">11</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">([</span><span class="mi">1</span><span class="p">,</span> <span class="mi">2</span><span class="p">,</span> <span class="mi">3</span><span class="p">],</span> <span class="n">marker</span><span class="o">=</span><span class="n">matplotlib</span><span class="o">.</span><span class="n">markers</span><span class="o">.</span><span class="n">CARETDOWNBASE</span><span class="p">)</span>
</pre>
    </button></div>
</div>
<p>Examples showing the use of markers:</p>
<ul class="simple">
<li><p><a class="reference internal" href="../gallery/lines_bars_and_markers/marker_reference.html"><span class="doc">Marker reference</span></a></p></li>
<li><p><a class="reference internal" href="../gallery/lines_bars_and_markers/scatter_star_poly.html"><span class="doc">Marker examples</span></a></p></li>
</ul>
<section id="classes">
<h2>Classes<a class="headerlink" href="#classes" title="Permalink to this headline">¶</a></h2>
<table class="longtable table autosummary">
<colgroup>
<col style="width: 10%">
<col style="width: 90%">
</colgroup>
<tbody>
<tr class="row-odd"><td><p><a class="reference internal" href="_as_gen/matplotlib.markers.MarkerStyle.html#matplotlib.markers.MarkerStyle" title="matplotlib.markers.MarkerStyle"><code class="xref py py-obj docutils literal notranslate"><span class="pre">MarkerStyle</span></code></a>([marker,&nbsp;fillstyle])</p></td>
<td><p>A class representing marker types.</p></td>
</tr>
</tbody>
</table>
</section>
</section>
</div>