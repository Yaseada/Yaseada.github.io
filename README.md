This repo allows to register together longitudinal abdominal CT-Scans
Align livers from different acquisitions. Conceptually, there are three types of registration (one single method might be able to solve all of them):

- Intra-exam, for exams at the same day with one modality, the goal is to align sequences acquired with contrast injection.
- Longitudinal, for exams acquired at different days with one modality, the goal is to align sequences in order to track the lesion growth. (Note: registration can change volumetric measures).
- Multi-modal, for exams acquired with different image modalities (CT and MRI),

## Liver Registration
This repo allows to register together abdominal CT scans from a same patient at different days. This code is specific to the `/export/projects/Candela/session_01` dataset but is a good example on how one can use [Elastix](https://github.com/SuperElastix/elastix/wiki), a toolbox for rigid and nonrigid registration of (medical) images.

A complete documentation on this specific project is available on [confluence](https://imagia.atlassian.net/wiki/spaces/CAN/pages/19071005/Registration+methods). 

## Dataset and preprocessing

## Requirements

## LabelOverlapMeasuresImageFilter

## Results

## Potential applications
Elastix can be used for other type of registration, for example it yielded great results in CT/MRI alignment: 

| Method | CT/MRI | CT/MRI| CT/MRI|
| -------- | -------- | -------- | ------- |
| After affine registration (from top to bottom of the liver presented from left to right respectively). **Fixed CT image** = green (obtained with MITK) **Moved MRI image** = red. One can appreciate the mismatch between fixed and moved kidneys.    | ![](https://api.media.atlassian.com/file/21fb155e-36a3-43b4-b871-8113bbc80e5b/image?mode=full-fit&client=67cf4da6-9197-47a2-ac00-84dfef05751a&token=eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiI2N2NmNGRhNi05MTk3LTQ3YTItYWMwMC04NGRmZWYwNTc1MWEiLCJhY2Nlc3MiOnsidXJuOmZpbGVzdG9yZTpmaWxlOjIxZmIxNTVlLTM2YTMtNDNiNC1iODcxLTgxMTNiYmM4MGU1YiI6WyJyZWFkIl19LCJleHAiOjE1MjQyNDA5MTksIm5iZiI6MTUyNDIzNzU1OX0.PXjowwuXTyHnqOq76kf9mt2n3DnN7MS-dLRdVyWoGa0)     | ![](https://api.media.atlassian.com/file/0d387470-71ff-4f44-8190-5a916ec2ecc8/image?mode=full-fit&client=67cf4da6-9197-47a2-ac00-84dfef05751a&token=eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiI2N2NmNGRhNi05MTk3LTQ3YTItYWMwMC04NGRmZWYwNTc1MWEiLCJhY2Nlc3MiOnsidXJuOmZpbGVzdG9yZTpmaWxlOjBkMzg3NDcwLTcxZmYtNGY0NC04MTkwLTVhOTE2ZWMyZWNjOCI6WyJyZWFkIl19LCJleHAiOjE1MjQyNDA5NTAsIm5iZiI6MTUyNDIzNzU5MH0.dBhf3-WCh3-hlAeZU-j5ONqcD_szU1nQeDbwqQPxOTA)    | ![](https://api.media.atlassian.com/file/ee296ce8-5641-48ab-a095-9f744e2e90aa/image?mode=full-fit&client=67cf4da6-9197-47a2-ac00-84dfef05751a&token=eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiI2N2NmNGRhNi05MTk3LTQ3YTItYWMwMC04NGRmZWYwNTc1MWEiLCJhY2Nlc3MiOnsidXJuOmZpbGVzdG9yZTpmaWxlOmVlMjk2Y2U4LTU2NDEtNDhhYi1hMDk1LTlmNzQ0ZTJlOTBhYSI6WyJyZWFkIl19LCJleHAiOjE1MjQyNDA5NTAsIm5iZiI6MTUyNDIzNzU5MH0.ous0EPEXAdv5nkSLkcCyOffPdhtQJ1a5pmlnKlVdmxE) |
| After affine registration followed by a non-rigid registration. One can see a better overlap between fixed and moved kidneys.  | ![](https://api.media.atlassian.com/file/d1e33e7a-aed7-436e-b7be-2e1bd7dcfcbe/image?mode=full-fit&client=67cf4da6-9197-47a2-ac00-84dfef05751a&token=eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiI2N2NmNGRhNi05MTk3LTQ3YTItYWMwMC04NGRmZWYwNTc1MWEiLCJhY2Nlc3MiOnsidXJuOmZpbGVzdG9yZTpmaWxlOmQxZTMzZTdhLWFlZDctNDM2ZS1iN2JlLTJlMWJkN2RjZmNiZSI6WyJyZWFkIl19LCJleHAiOjE1MjQyNDA4MzgsIm5iZiI6MTUyNDIzNzQ3OH0.XEk1QxwiS1tYWb-nhk9ufKH_SUjNAY0WCBElG4oKXCk) | ![](https://api.media.atlassian.com/file/4b1efd8e-05ea-417e-85a0-463c4b79f2db/image?mode=full-fit&client=67cf4da6-9197-47a2-ac00-84dfef05751a&token=eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiI2N2NmNGRhNi05MTk3LTQ3YTItYWMwMC04NGRmZWYwNTc1MWEiLCJhY2Nlc3MiOnsidXJuOmZpbGVzdG9yZTpmaWxlOjRiMWVmZDhlLTA1ZWEtNDE3ZS04NWEwLTQ2M2M0Yjc5ZjJkYiI6WyJyZWFkIl19LCJleHAiOjE1MjQyNDA4NzAsIm5iZiI6MTUyNDIzNzUxMH0.H-J3snUFQXjnSH2NyLc8zzn6kIAG0JFcWjGw0tSJXYo) | ![](https://api.media.atlassian.com/file/bc002ded-4a62-4215-9ae5-5628daaa013c/image?mode=full-fit&client=67cf4da6-9197-47a2-ac00-84dfef05751a&token=eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiI2N2NmNGRhNi05MTk3LTQ3YTItYWMwMC04NGRmZWYwNTc1MWEiLCJhY2Nlc3MiOnsidXJuOmZpbGVzdG9yZTpmaWxlOmJjMDAyZGVkLTRhNjItNDIxNS05YWU1LTU2MjhkYWFhMDEzYyI6WyJyZWFkIl19LCJleHAiOjE1MjQyNDA4OTYsIm5iZiI6MTUyNDIzNzUzNn0.PzXMWi7FY3AgRxSnyXRJ1re3qMpxsxNR94Fcb5o090E) |
