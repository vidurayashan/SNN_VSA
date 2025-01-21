# Spiking Neural Network Implementation of Fourier Holographic Reduced Representations (FHRR)

This repository contains the code for implementing **Fourier Holographic Reduced Representations (FHRR)** within **Spiking Neural Networks (SNNs)**, leveraging the **Lava** neuromorphic computing framework. This project explores the potential of FHRR as a middle-layer abstraction to bridge the gap between neuromorphic hardware and practical real-world applications.

## Overview

Neuromorphic computing offers advantages over conventional von Neumann architectures, including **energy efficiency, parallelism, scalability, and stochasticity**. SNNs, inspired by biological neural networks, are a natural fit for implementing neuromorphic computing systems. However, the development of practical applications is hindered by a lack of a unifying computing framework that connects neuromorphic computing and application functionality.

**Vector Symbolic Architectures (VSA)**, and particularly **FHRR**, offer a promising solution by providing a distributed vector representation of symbolic and numerical data structures. This project investigates FHRR as a middle-layer VSA abstraction for developing practical, real-world neuromorphic applications.

## Key Features

*   **Spike Encoding Library for FHRR:** The core of this repository is a custom library for encoding and decoding FHRR vectors using spike trains.
*   **Lava Framework Implementation:** The library is built using **Lava**, an open-source framework for neuromorphic computing, making it compatible with neuromorphic hardware like the Intel Loihi chip.
*   **Spike-Based Operations:** The library implements essential VSA operations like **binding, superposition, and similarity measurement** using spike-based computations.
*  **Online Decoding:** The decoding algorithm is designed to work **online**, meaning it can process spike trains in real-time without the need for post-processing. This enables applications in areas like sensory processing, robotics, and cognitive computing.
*   **Modular Design:** The library is designed to be modular, allowing for easy expansion and customization with the following modules:
    *   **Encoding:** Converts numerical values to spike trains using Leaky-Integrate-and-Fire (LIF) neurons, where the time to the first spike is inversely proportional to the encoded value.
    *   **Decoding:** Recovers the original numerical values from the incoming spike trains.
    *   **Superposition:** Combines multiple FHRR vectors into a single vector.
    *   **Binding:** Associates two FHRR vectors together to represent a relationship.
    *  **Error Correction:**  (Future work, not yet implemented).

## Proposed Algorithm

The proposed algorithm includes the following two main components:

*   **Encoder:** Uses a population of **Leaky-Integrate-and-Fire (LIF) neurons** to convert numerical values into delayed spikes. The delay to the first spike is controlled by the bias of the LIF neuron, making it inversely proportional to the encoded value.
*   **Decoder:** Receives spike trains and converts them back to numerical values based on the time between the spikes. It employs a novel vector computation algorithm that can process the receiving spike streams in parallel. The decoder does not require any post-processing and functions in real-time as spikes arrive.

## Experiments

The repository includes experiments to evaluate the performance of the proposed algorithm.

*   **Reconstruction Similarity:** Evaluates the accuracy of the encoding and decoding process by comparing the original and reconstructed vectors using the cosine similarity metric. Experiments show that **latency-based coding schemes** show higher reconstruction similarity compared to rate-based coding.
*   **Activity Analysis:** Measures the number of spikes required by each neural coding scheme for different vector dimensions.
*   **Distributed Records:** Demonstrates the use of the library in a distributed records scenario where table-like records are represented with hypervectors. The results indicate that the proposed method accurately retrieves and processes records using binding and superposition operations.

## Usage

1.  Clone the repository.
2.  Install the required dependencies, including the Lava framework.
3.  Explore the example scripts to understand how to use the library.
4.  Adapt the library to your specific neuromorphic computing application.

## Future Work

*   Develop more biologically plausible methods for VSA operations within the spiking domain.
*   Implement error correction modules.
*   Test the library on neuromorphic hardware (e.g., Intel Loihi).
*   Evaluate the library on more complex real-world tasks.

##  Contributions
Contributions are welcome! Please fork the repository and submit a pull request.
