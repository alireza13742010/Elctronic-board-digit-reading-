# Elctronic-board-digit-reading-
This is the resposiory to read digit from the electronic device and report the number.

<p align="justify"> Qwen2.5-VL is a single, end-to-end vision-language model that unifies text detection and recognition. To get started, you’ll install the Hugging Face Transformers library (and any Qwen-VL utilities), then load both the Qwen2_5_VLForConditionalGeneration model and its corresponding AutoProcessor from the “Qwen/Qwen2.5-VL-7B-Instruct” checkpoint. Under the hood, the processor handles image preprocessing (resizing, normalization) and tokenizes your chat-style prompt, while the model—running on CPU/GPU—learns to map pixels directly to text tokens without a separate OCR engine. </p>

<p align="justify"> Once everything’s initialized, you construct a chat message that embeds your target image plus a user instruction like “Extract all text.” Pass that through the processor to get image tensors and token IDs, then call model.generate() to produce raw token outputs. Finally, decode those tokens with the processor’s batch_decode() to retrieve the recognized text. For the best accuracy, feed high-resolution scans, specify output formats (e.g. CSV or JSON), and if you’re parsing structured layouts (tables, receipts), prompt the model to return bounding boxes or CSV rows.  </p>

<p align="justify"> This repository evaluated several QWEN model versions and selected the one that performs best at digit recognition. </p>

The proposed approach unfolds in three core phases:

Preprocessing – an edge‐detection network first processes each digit image to delineate its contours.

Digit recognition – a detection model then takes those boundary‐enhanced outputs to identify the digits.

Validation & refinement – the phase-2 predictions are reviewed, and the model is fine-tuned based on that feedback.

# Result
<p align="center">
  <img src="https://github.com/user-attachments/assets/c37c9fb8-a79c-4796-b7c9-16ba5fe56059" width="350" title="Generated Image">
  <img src="https://github.com/user-attachments/assets/bdf3255c-1e78-40bf-8ac8-35b5ec59ba45" width="350" title="Generated Image">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/00917038-2415-4029-94d5-7537baa12a20" width="350" title="Generated Image">
  <img src="https://github.com/user-attachments/assets/d4cec710-4324-4156-9a2f-7a60824cd523" width="350" title="Generated Image">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/44e626bb-d1fa-490a-b28b-25ea251956a2" width="350" title="Generated Image">
  <img src="https://github.com/user-attachments/assets/374b2f36-4724-45ff-870c-a5fe2e48809b" width="350" title="Generated Image">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/7108d9bb-84a2-441d-937e-1ed18d177675" width="350" title="Generated Image">
  <img src="https://github.com/user-attachments/assets/5bd4c754-c40b-43ad-bca3-838eadd01145" width="350" title="Generated Image">
</p>

