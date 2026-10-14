# Awesome Spatial Memory [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated reading list on how visual systems **maintain, update, and retrieve spatial information over time**.

Spatial memory enables a system to reason beyond its current view: reconstructing places from sequential observations, remembering objects after they disappear, and using past spatial evidence to understand or act in the world. This repository connects research in streaming 3D perception, object permanence, and memory-augmented vision-language and embodied systems.

## Contents

- [Scope](#scope)
- [Foundations](#foundations)
- [Scene Memory](#scene-memory)
- [Object Memory](#object-memory)
- [Spatial Memory in VLMs and Embodied Agents](#spatial-memory-in-vlms-and-embodied-agents)
- [Benchmarks and Evaluation](#benchmarks-and-evaluation)
- [Background and Related Resources](#background-and-related-resources)

## Scope

We focus on **memory built from sequential visual observations**, including explicit maps or object stores, recurrent or latent states, adaptive weights, and retrieval mechanisms. A paper is particularly relevant when it addresses at least one of the following questions:

- **What to remember:** Which spatial observations, representations, or object states should persist?
- **How to update:** How should memory change as new views arrive, without excessive forgetting or drift?
- **How to retrieve:** How can a model access previously observed spatial information when needed?
- **How to evaluate:** Can a model retain spatial knowledge over occlusions, revisits, and long visual sequences?

The sections below are organized mainly by the **kind of spatial information remembered**. Subsections describe methodological themes and are not intended to be mutually exclusive. General-purpose 3D reconstruction and tracking methods are included as background only when they help explain spatial memory.

The list is organized by research topic, with newer publications first within each section. Each entry includes a paper link and a brief description of its relevance to spatial memory; official code and project links are added when available.

## Foundations

Foundational ideas from cognitive science and neural memory mechanisms.

- **Gated Delta Networks: Improving Mamba2 with Delta Rule** — *ICLR 2025* · [Paper](https://arxiv.org/abs/2412.06464)  
  Studies gated delta-rule updates for recurrent sequence memory.
- **Learning to (Learn at Test Time): RNNs with Expressive Hidden States** — *2024* · [Paper](https://arxiv.org/abs/2407.04620)  
  Explores test-time learning as a mechanism for updating hidden states.
- **Capturing the Objects of Vision with Neural Networks** — *2021* · [Paper](https://arxiv.org/abs/2109.03351)  
  Reviews computational accounts of object representations and their relationship to human visual cognition.
- **Linear Transformers Are Secretly Fast Weight Programmers** — *ICML 2021* · [Paper](https://arxiv.org/abs/2102.11174)  
  Connects linear attention to fast-weight memory updates.

## Scene Memory

Memory for continuously integrating observations of a physical environment, including scene geometry, camera motion, and long-term spatial consistency.

### Explicit Spatial Memory

- **Mem3R: Streaming 3D Reconstruction with Hybrid Memory via Test-Time Training** — *2026* · [Paper](https://arxiv.org/abs/2604.07279)  
  Combines explicit mapping state with an implicit fast-weight memory for camera tracking.
- **Anchor3R: Streaming 3D Reconstruction with Transient Anchors for Long-Horizon Visual Mapping** — *2026* · [Paper](https://arxiv.org/abs/2606.05035)  
  Uses transient anchoring and relative-pose structure for long-horizon visual mapping.
- **Spann3R: 3D Reconstruction with Spatial Memory** — *3DV 2025* · [Paper](https://arxiv.org/abs/2408.16061)  
  Maintains an explicit spatial memory for incremental 3D reconstruction.
- **Point3R: Streaming 3D Reconstruction with Explicit Spatial Pointer Memory** — *NeurIPS 2025* · [Paper](https://arxiv.org/abs/2507.02863) · [Code](https://github.com/YkiWu/Point3R) · [Project](https://ykiwu.github.io/Point3R/)  
  Uses pointer-based spatial memory for streaming reconstruction.
- **LONG3R: Long Sequence Streaming 3D Reconstruction** — *ICCV 2025* · [Paper](https://openaccess.thecvf.com/content/ICCV2025/papers/Chen_LONG3R_Long_Sequence_Streaming_3D_Reconstruction_ICCV_2025_paper.pdf)  
  Addresses reconstruction from long sequential image streams.

### Recurrent and Latent State

- **CUT3R: Continuous 3D Perception Model with Persistent State** — *CVPR 2025* · [Paper](https://arxiv.org/abs/2501.12387)  
  Carries a persistent state across observations for continuous 3D perception.
- **Wint3R: Window-Based Streaming Reconstruction with Camera Token Pool** — *2025* · [Paper](https://arxiv.org/abs/2509.05296)  
  Studies window-based streaming reconstruction with a camera-token pool.

### Memory Updates and Test-Time Adaptation

- **TTT3R: 3D Reconstruction as Test-Time Training** — *ICLR 2026* · [Paper](https://arxiv.org/abs/2509.26645)  
  Investigates test-time training for updating streaming reconstruction state.
- **TTSA3R: Training-Free Temporal-Spatial Adaptive Persistent State for Streaming 3D Reconstruction** — *2026* · [Paper](https://arxiv.org/abs/2601.22615)  
  Adapts a persistent reconstruction state without additional model training.
- **MeMix: Writing Less, Remembering More for Streaming 3D Reconstruction** — *2026* · [Paper](https://arxiv.org/abs/2603.15330)  
  Studies selective memory writing for streaming geometry.
- **Rethinking the State Update Gate for Long-Sequence Recurrent 3D Reconstruction** — *2026* · [Paper](https://arxiv.org/abs/2605.16981)  
  Examines update gating in long-sequence recurrent reconstruction.
- **ReCal3R: Reliability-Calibrated Learning Rates for Streaming 3D Reconstruction** — *2026* · [Paper](https://arxiv.org/abs/2607.05356)  
  Calibrates state adaptation using reliability estimates.
- **ZipMap: Linear-Time Stateful 3D Reconstruction via Test-Time Training** — *2026* · [Paper](https://arxiv.org/abs/2603.04385)  
  Uses test-time training in a linear-time stateful mapping framework.
- **Scal3R: Scalable Test-Time Training for Large-Scale 3D Reconstruction** — *2026* · [Paper](https://arxiv.org/abs/2604.08542)  
  Explores scalable test-time adaptation for large-scale reconstruction.

### Causal and Cache-Based Memory

- **STream3R: Scalable Sequential 3D Reconstruction with Causal Transformer** — *ICLR 2026* · [Paper](https://arxiv.org/abs/2508.10893) · [Code](https://github.com/NIRVANALAN/STream3R)  
  Models sequential 3D reconstruction with a causal transformer.
- **STAC: Plug-and-Play Spatio-Temporal Aware Cache Compression for Streaming 3D Reconstruction** — *CVPR 2026* · [Paper](https://arxiv.org/abs/2603.20284)  
  Compresses spatiotemporal caches for streaming 3D reconstruction.
- **FrameVGGT: Coherence-Preserving Memory for Bounded Streaming Geometry** — *2026* · [Paper](https://arxiv.org/abs/2603.07690)  
  Studies bounded memory for coherent streaming geometry.
- **LongStream: Long-Sequence Streaming Autoregressive Visual Geometry** — *2026* · [Paper](https://arxiv.org/abs/2602.13172)  
  Investigates autoregressive geometry estimation over long sequences.
- **StreamVGGT: Streaming 4D Visual Geometry Transformer** — *2025* · [Paper](https://arxiv.org/abs/2507.11539)  
  Extends visual geometry modeling to streaming 4D inputs.

### Long-Horizon Consistency and Revisiting

- **Geometric Context Transformer for Streaming 3D Reconstruction (LingBot-Map)** — *2026* · [Paper](https://arxiv.org/abs/2604.14141)  
  Uses geometric context for streaming scene reconstruction.
- **NoDrift3R: Raymap-Guided Coupling for Drift-Robust Unposed Feed-Forward 3D Reconstruction** — *2026* · [Paper](https://arxiv.org/abs/2607.07168)  
  Targets drift robustness in unposed reconstruction.
- **VGGT-Align: Bridging Local Reconstruction and Global Consistency for Long-Sequence 3D Reconstruction** — *2026* · [Paper](https://arxiv.org/abs/2608.15260)  
  Connects local estimates to globally consistent long-sequence geometry.
- **CLoSeR: Closing the Loop for Long-Context Streaming Reconstruction** — *NeurIPS 2026* · [Paper](https://arxiv.org/abs/2610.01927)  
  Addresses revisiting and loop closure in long-context streaming reconstruction.

## Object Memory

Memory for object identity, location, and state across changing views, disappearance, and occlusion.

### Long-Term Object Tracking and Segmentation

- **A Distractor-Aware Memory for Visual Object Tracking with SAM2 (DAM4SAM)** — *CVPR 2025* · [Paper](https://arxiv.org/abs/2411.17576)  
  Uses distractor-aware memory to improve visual tracking.
- **SAMITE: Position Prompted SAM2 with Calibrated Memory for Visual Object Tracking** — *2025* · [Paper](https://arxiv.org/abs/2507.21732)  
  Investigates memory calibration for SAM2-based tracking.
- **SAMURAI: Adapting Segment Anything Model for Zero-Shot Visual Tracking with Motion-Aware Memory** — *2024* · [Paper](https://arxiv.org/abs/2411.11922)  
  Adds motion-aware memory to SAM-based object tracking.
- **XMem: Long-Term Video Object Segmentation with an Atkinson-Shiffrin Memory Model** — *ECCV 2022* · [Paper](https://arxiv.org/abs/2207.07115)  
  Organizes video object segmentation memory across multiple temporal scales.

### Object Permanence and Occlusion

- **Tracking Is Not Permanence: What Video World Models Keep of a Hidden Object** — *2026* · [Paper](https://arxiv.org/abs/2610.07355)  
  Examines whether video models retain information about hidden objects beyond tracking.
- **Learning Object Permanence from Videos via Latent Imaginations (Loci-Looped)** — *2023* · [Paper](https://arxiv.org/abs/2310.10372)  
  Uses latent imagination to model persistent objects beyond direct visibility.
- **Out of Sight, Still in Mind: Reasoning and Planning about Unobserved Objects with Video Tracking Enabled Memory Models** — *2023* · [Paper](https://arxiv.org/abs/2309.15278)  
  Connects memory of unobserved objects to reasoning and planning.
- **Learning to Track with Object Permanence** — *ICCV 2021* · [Paper](https://arxiv.org/abs/2103.14258)  
  Maintains recurrent object information to track locations and identities through occlusion.
- **Learning Object Permanence from Video** — *ECCV 2020* · [Paper](https://arxiv.org/abs/2003.10469)  
  Studies learning object persistence from visual observations.

### Amodal Object Tracking

- **Track Anything Behind Everything: Zero-Shot Amodal Video Object Segmentation** — *2024* · [Paper](https://arxiv.org/abs/2411.19210)  
  Extends segmentation to object regions that are not directly visible.
- **Tracking through Containers and Occluders in the Wild (TCOW)** — *CVPR 2023* · [Paper](https://arxiv.org/abs/2305.03052)  
  Studies tracking when objects are hidden by containers or occluders.

## Spatial Memory in VLMs and Embodied Agents

Methods that use remembered spatial evidence for language-grounded reasoning, exploration, or embodied decisions.

- **Spatial-TTT: Streaming Visual-Based Spatial Intelligence with Test-Time Training** — *ECCV 2026* · [Paper](https://arxiv.org/abs/2603.12255) · [Code](https://github.com/THU-SI/Spatial-TTT)  
  Updates fast-weight memory from streaming video to support long-horizon spatial reasoning.
- **Reasmory: 3D Reconstruction as Explicit Memory for VLMs Spatial Reasoning** — *2026* · [Paper](https://arxiv.org/abs/2606.00963)  
  Makes reconstructed 3D structure accessible as explicit memory for a VLM.
- **Stream3D-VLM: Online 3D Spatial Understanding with Incremental Geometry Priors** — *2026* · [Paper](https://arxiv.org/abs/2606.06891)  
  Incorporates incremental geometric evidence into online VLM spatial understanding.
- **LongSpace: Exploring Long-Horizon Spatial Memory from Perception to Recall in Video** — *2026* · [Paper](https://arxiv.org/abs/2606.05677)  
  Builds retrievable spatial memory across long video sequences and introduces LongSpace-Bench.
- **3D-Mem: 3D Scene Memory for Embodied Exploration and Reasoning** — *CVPR 2025* · [Paper](https://arxiv.org/abs/2411.17735) · [Code](https://github.com/UMass-Embodied-AGI/3D-Mem)  
  Stores scene snapshots and retrieves them for embodied exploration and question answering.
- **Vision-Language Memory for Spatial Reasoning (VLM²)** — *2025* · [Paper](https://arxiv.org/abs/2511.20644)  
  Studies vision-language memory for spatial reasoning.
- **DynaMem: Online Dynamic Spatio-Semantic Memory for Open World Mobile Manipulation** — *2024* · [Paper](https://arxiv.org/abs/2411.04999)  
  Maintains an online spatio-semantic scene memory for robotic object search and manipulation.
- **End-to-End Egospheric Spatial Memory** — *ICLR 2021* · [Paper](https://arxiv.org/abs/2102.07764)  
  Learns an egocentric spatial memory for embodied perception and behavior.

## Benchmarks and Evaluation

Resources for measuring retention and retrieval of spatial knowledge, rather than only reconstruction or per-frame recognition accuracy.

- **LongSpace-Bench** — *2026* · [Paper](https://arxiv.org/abs/2606.05677)  
  Evaluates long-horizon spatial perception, relationships, and memory from room-tour videos.
- **Ego4D Episodic Memory** · [Benchmark](https://ego4d-data.org/docs/benchmarks/episodic-memory/)  
  Includes visual queries about previously encountered objects in egocentric video.
- **VSI-Bench** · [Benchmark](https://github.com/vision-x-nyu/thinking-in-space)  
  Evaluates video-based spatial reasoning; included as a related evaluation resource rather than a dedicated online-memory benchmark.

## Background and Related Resources

The works below inform spatial memory, but do not necessarily propose a persistent memory mechanism themselves.

### Geometric Perception and SLAM

- **VGGT: Visual Geometry Grounded Transformer** — *CVPR 2025* · [Paper](https://arxiv.org/abs/2503.11651)  
  Predicts multiple geometric quantities in a unified feed-forward framework.
- **DUSt3R: Geometric 3D Vision Made Easy** — *CVPR 2024* · [Paper](https://arxiv.org/abs/2312.14132)  
  Introduces learned pairwise geometry prediction for 3D vision.
- **Grounding Image Matching in 3D with MASt3R** — *ECCV 2024* · [Paper](https://arxiv.org/abs/2406.09756)  
  Builds geometry-aware image matching on 3D predictions.
- **ORB-SLAM3** — *T-RO 2021* · [Paper](https://arxiv.org/abs/2007.11898)  
  Provides a classical visual and visual-inertial SLAM foundation.
- **DROID-SLAM** — *NeurIPS 2021* · [Paper](https://arxiv.org/abs/2108.10869)  
  Provides a learned SLAM approach for camera tracking and mapping.

### Related Awesome Lists

- [Awesome DUSt3R](https://github.com/ruili3/awesome-dust3r) - Related work on DUSt3R-style geometric foundation models.
- [Awesome Feed-Forward 3D](https://github.com/ziplab/Awesome-Feed-Forward-3D) - Research on feed-forward 3D scene modeling.
- [Awesome Memory for Robotics](https://github.com/Everloom-129/Awesome-Memory-for-Robotics) - Broader research on memory systems used in robotics.
- [Awesome 4D Spatial Intelligence](https://github.com/yukangcao/Awesome-4D-Spatial-Intelligence) - A broader collection of 3D and 4D reconstruction literature.

## Contributing

Suggestions, corrections, and pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for selection criteria and formatting guidelines.
