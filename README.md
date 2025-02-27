# Speaker Verification
Speaker verification is verifying the identity of a person from characteristics of the voice independent from language via NVIDIA NeMo.

This reporisitory presents three NeMo speaker verification models: 
- [SpeakerNet](https://catalog.ngc.nvidia.com/orgs/nvidia/teams/nemo/models/speakerverification_speakernet)
- [TitaNet-L](https://catalog.ngc.nvidia.com/orgs/nvidia/teams/nemo/models/titanet_large)
- [ECAPA-TDNN](https://catalog.ngc.nvidia.com/orgs/nvidia/teams/nemo/models/ecapa_tdnn)

#### Download Models - Save and Load Speaker Vectors
You can download Nemo models and speaker vectors for SpeakerNet, TitaNet-L, ECAPA-TDNN from `files/`.

#### Prediction
The cosine similarity metric was used for prediction.
```python
from sklearn.metrics.pairwise import cosine_similarity
sims = cosine_similarity([vector[0]], speakers_vectors)[0]
```
To predict most similar speaker in `test_voices/` refered to `ref_voices` run the following command:
```python
python speaker_verification.py
```

#### Inference Benchmark
- Torch Model
- Onnx Model
Run the script below to compare the inference time of SpeakerNet model. 
```python
speaker_verification_with_torch_and_onnx.ipynb
```




