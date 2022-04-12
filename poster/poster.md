---
marp: true
theme: poster
paginate: false
size: 44:33
---

<div class="header">
<div>

<!-- <div class=center_container> -->

![headerlogo](./images/../../../images/hopkins-logo.png)

<!-- <br>
<br>
<br>

### Summary -->

<!-- </div> -->

</div>
<div>

<!-- # Is a whole insect brain connectome bilaterally symmetric? <br> A case study on comparing two networks -->

# Generative network modeling reveals a quantitative definition <br> of bilateral symmetry exhibited by a whole insect brain connectome

<!-- # Towards statistical comparative connectomics:<br> A case study on the bilateral symmetry of an insect brain connectome -->


## Benjamin D. Pedigo<span class=super>1*</span>, Mike Powell<span class=super>1</span>, Eric W. Bridgeford<span class=super>1</span>, Michael Winding<span class=super>2</span>, Carey E. Priebe<span class=super>1</span>, Joshua T. Vogelstein<span class=super>1</span>

##### 1 - Johns Hopkins University, 2 - University of Cambridge, $\ast$ - correspondence: ![icon](../../images/email.png) [_bpedigo@jhu.edu_](mailto:bpedigo@jhu.edu) ![icon](../../images/github.png) [_@bdpedigo (Github)_](https://github.com/bdpedigo) ![icon](../../images/twitter.png) [_@bpedigod (Twitter)_](https://twitter.com/bpedigod) ![icon](../../images/web.png) [_bdpedigo.github.io_](https://bdpedigo.github.io/) 

</div>
<div>

![headerlogo](./images/../../../images/nd_logo.png)

<span style="text-align:center; margin:0; padding:0">

<!-- ### [neurodata.io](https://neurodata.io/) -->

</span>

</div>
</div>


<!-- # Towards statistical comparative connectomics:<br> A case study on the bilateral symmetry of an insect brain connectome -->


<span class='h3-noline'> Summary </span>

<div class='box'>
<div class="columns5">
<div>

<!-- #### Summary -->

- Aimed to define bilateral symmetry for a connectome, and formally test this hypothesis.

</div>
<div>

- Hemispheres differ in a network-wide parameter under even the simplest model of a network pair.

</div>
<div>

- Hemispheres differ in neuron group connection probabilities, even when adjusting for the network-wide effect.

</div>
<div>

- Detect no differences in adjusted group connections after removing a cell type or when only considering strong edges.

<!-- - Removing a specific cell type and adjusting for this network-wide effect provides one notion of bilateral symmetry -->

<!-- 
- Difference between hemispheres can be explained as combination of network-wide and cell type-specific effects -->

</div>
<div>

- Provided a definition of bilateral symmetry exhibited by this connectome, tools for future connectome comparisons

</div>
</div>
</div>

<div class="columns3">
<div>


### Motivation

- Connectomes are rich sources of inspiration for architectures in artificial intelligence.
- Comparing connectomes could help elucidate which structural features are necessary for yielding the capabilities animal intelligences.
- Bilateral symmetry for connectomes is one such comparison; has been investigated, but not clearly defined as a network hypothesis.

<!-- - We explored statistically principled connectome comparison via a case study of a *Drosophila* larva connectome -->

### Larval *Drosophila* brain connectome

<!-- START subcolumns -->
<div class=columns2>
<div>

![center w:5.5in](./../../images/Figure1-brain-render.png)

**Fig 1A:** 3D rendering of a larval *Drosophila* brain connectome [1] comprised of ~3k neurons and ~544k synapses.

</div>
<div>

![center w:5.1in](./../../../results/figs/show_data/adjacencies.png)

**Fig 1B:** Directed, binary adjacency matrix sorted by brain hemisphere. We compare $\color{#66c2a5} L \rightarrow L$ vs. $\color{#fc8d62} R \rightarrow R$ subgraphs.

</div>
</div>

<!-- - Connectome of a larval *Drosophila* [1] has xxx neurons and xxx synapses -->

<!-- END subcolumns -->

<!-- ![center](../../../results/figs/show_data/adj_and_layout.png) -->

## Are the <span style="color:var(--left)"> left </span> and <span style="color:var(--right)"> right </span> networks "different"?
<br>

<!-- - Two sample testing problem! But for networks -->
Requires that we define what we could mean by "different" for a pair of networks, develop a test procedure for each definition.

### Density test (Model 1)

<div class=columns2>
<div>

![](../../../results/figs/er_unmatched_test/er_methods.svg)

</div>
<div>

![](../../../results/figs/er_unmatched_test/er_density.svg)

</div>
</div>

<div class=columns2>
<div>


**Fig 2A:** Testing symmetry under Erdos-Renyi (ER) model [2] compares global connection probability  (density), here via Fisher's exact test.

</div>
<div>

**Fig 2B:** Test comparing densities rejected ($p{<}10^{-23}$), even the simplest model parameter differs between hemispheres.

</div>
</div>

</div>
<div>


### Group connection test (Model 2)

<!-- #### A -->
![center w:10.5in](./../../../results/figs/sbm_unmatched_test/sbm_methods_explain.svg)
**Fig 3A:** Testing under stochastic block model (SBM) compares probabilities of connections between groups (here using cell types [1]).

<!-- START subcolumns -->
<div class=columns2>
<div>

![](../../../results/figs/sbm_unmatched_test/sbm_uncorrected_pvalues.svg)

</div>
<div>

![center w:5in](../../../results/figs/sbm_unmatched_test/significant_p_comparison.svg)

</div>
</div>

<div class=columns2>
<div>

<!-- P-values for group connections. Test of equal group connections rejects ($p<10^{-8}$). -->

**Fig 3B:** Test comparing group connections rejected ($p{<}10^{-7}$); five specific connections differ.

</div>
<div>

**Fig 3C:** For significant group connections, denser hemisphere probability is always higher.

</div>
</div>

### Density-adjusted group connection test (Model 3)

<!-- ![](./../../../results/figs/adjusted_sbm_unmatched_test/adjusted_methods_explain.svg)

![](./../../../results/figs/adjusted_sbm_unmatched_test/sbm_pvalues.svg) -->

<!-- ![center w:14in](./../../../results/figs/adjusted_sbm_unmatched_test/adjusted_sbm_composite.svg) -->
<div class=columns2>
<div>

<br>

![center w:5in](./../../../results/figs/adjusted_sbm_unmatched_test/adjusted_methods_explain.svg)

</div>
<div>

![](./../../../results/figs/adjusted_sbm_unmatched_test/sbm_pvalues.svg)

</div>
</div>

<div class=columns2>
<div>

**Fig 4A:** Hypothesis from Fig 3 modified by a factor $c$ set to make densities equal.

</div>
<div>

**Fig 4B:** Test comparing adjusted group connections rejected $(p{<}10^{-2})$; differences from KCs.

</div>
</div>


</div>
<div>


<!-- ### Removing Kenyon cells -->

<!-- - Density test: $p < 10^{-26}$
- Group connection test: $p < 10^{-2}$
- Density-adjusted group connection test: $p \approx 0.5$ -->

<!-- ### Removing Kenyon cells
Reran all tests after removing the asymmetric cell type (see below) -->

### Notions of bilateral symmetry

<!-- <style scoped>
table {
    font-size: 0.3in;
    /* text-align: center; */
    /* margin-bottom: 50px; */
}
</style> -->

<div class="columns2">
<div>

#### With Kenyon cells
| Model |                       $H_0$ (vs. $H_A \neq$)                       |    p-value    |
| :---: | :----------------------------------------------------------------: | :-----------: |
| **1** |  $\color{#66c2a5} p^{(L)} \color{black} = \color{#fc8d62}p^{(R)}$  | ${<}10^{-23}$ |
| **2** | $\color{#66c2a5} B^{(L)} \color{black} = \color{#fc8d62} B^{(R)}$  | ${<}10^{-7}$  |
| **3** | $\color{#66c2a5}B^{(L)} \color{black}  = c \color{#fc8d62}B^{(R)}$ | ${<}10^{-2}$  |


</div>
<div>

#### Without Kenyon cells
| Model |                       $H_0$ (vs. $H_A \neq$)                       |    p-value    |
| :---: | :----------------------------------------------------------------: | :-----------: |
| **1** |  $\color{#66c2a5} p^{(L)} \color{black} = \color{#fc8d62}p^{(R)}$  | ${<}10^{-26}$ |
| **2** | $\color{#66c2a5} B^{(L)} \color{black} = \color{#fc8d62} B^{(R)}$  | ${<}10^{-2}$  |
| **3** | $\color{#66c2a5}B^{(L)} \color{black}  = c \color{#fc8d62}B^{(R)}$ |    $0.51$     |

</div>
</div>

<!-- #### With Kenyon cells
| Model  |                       $H_0$ (vs. $H_A \neq$)                       | p-value |
| :----- | :----------------------------------------------------------------: | :-----: |
| ER     |  $\color{#66c2a5} p^{(L)} \color{black} = \color{#fc8d62}p^{(R)}$  |    x    |
| SBM    | $\color{#66c2a5} B^{(L)} \color{black} = \color{#fc8d62} B^{(R)}$  |         |
| DA-SBM | $\color{#66c2a5}B^{(L)} \color{black}  = c \color{#fc8d62}B^{(R)}$ |         |

#### Without Kenyon cells
| Model  |                       $H_0$ (vs. $H_A \neq$)                       | p-value |
| :----- | :----------------------------------------------------------------: | :-----: |
| ER     |  $\color{#66c2a5} p^{(L)} \color{black} = \color{#fc8d62}p^{(R)}$  |    x    |
| SBM    | $\color{#66c2a5} B^{(L)} \color{black} = \color{#fc8d62} B^{(R)}$  |    d    |
| DA-SBM | $\color{#66c2a5}B^{(L)} \color{black}  = c \color{#fc8d62}B^{(R)}$ |         | --> |


### Edge weight thresholds

<!-- ![](../../../results/figs/thresholding_tests/edge_weight_dist_input_proportion.png) -->

<div class="columns2">
<div>

![](./results/thresholding_tests/../../../../../results/figs/thresholding_tests/thresholding_methods.svg)

</div>
<div>

![](../../../results/figs/thresholding_tests/input_threshold_pvalues_legend.svg)

</div>
</div>

<div class="columns2">
<div>

**Fig 5A:** Removed edges w/ weight (synapse count or percentage of input to downstream neuron) below some threshold, tested symmetry for each pair of networks. 

</div>
<div>

**Fig 5B:** Did not detect asymmetry in networks of only top ~$50\%$ of edges (by input percentage) under models studied here. Not true using synapse counts edge weights (not shown).

</div>
</div>

### Limitations and extensions
- Other models to consider (e.g. random dot product graph [3])
- Other sensible neuron groupings for group connection test
- Matching nodes across networks leads to new models, likely more power

###


<div class="columns2">
<div>

#### Code

<div class="columns3-np">
<div>

![left h:1in](./../../images/graspologic_svg.svg)

</div>
<div>

[![h:.4in](https://pepy.tech/badge/graspologic)](https://pepy.tech/project/graspologic) 
[![h:.4in](https://img.shields.io/github/stars/microsoft/graspologic?style=social)](https://github.com/microsoft/graspologic)

</div>
<div>

![center h:1in](./../../images/graspologic-qr.svg)

</div>
</div>

<br>

<div class="columns3-np">
<div>

This work 

</div>
<div>

[![h:0.4in](https://jupyterbook.org/badge.svg)](http://docs.neurodata.io/bilateral-connectome/)

</div>
<div>


![center h:1in](./../../images/bilateral-qr.svg)

</div>
</div>

#### Acknowledgements
<footer>
Marta Zlatic's lab, Albert Cardona's lab and all tracers for the amazing dataset and many ideas. NeuroData lab for feedback. Many at Microsoft Research for w/ graspologic.
</footer>

</div>
<div>

#### References

<footer>
[1] Winding, Pedigo et al. "The complete connectome of an insect brain," In preparation (2022) 
<br>
[2] Chung et al. "Statistical connectomics," Ann. Rev. Statistics and its Application (2021) <br>
[3] Athreya et al. "Statistical inference on random dot product graphs: a survey," JMLR (2017)
</footer>

#### Funding
<!-- ![h:1in](../../images/NSF_4-Color_bitmap_Logo.png) -->

<footer>
B.D.P. supported by the NSF GRFP (DGE1746891). J.T.V. supported by NSF CAREER Award (1942963). J.T.V + C.E.P supported by NIH BRAIN Initiative (RF1MH123233). Findings and conclusions expressed are  those of the authors and not necessarily those of the funders.
</footer>

</div>
</div>




<!-- <div class='references'>


</div> -->

</div>
</div>

