# Create Training Data

### Image Retrieval


### Image Inpainting

### Prompt for image inpainting captions

```
# Create background replacement
python create_augmentation_mask.py --image_folder ../../data/minibo/ --output_folder /mnt/localssd/code/data/minibo
python create_augmentation_mask.py --image_folder ../../data/minimam/ --output_folder /mnt/localssd/code/data/minimam  

python sdxl-inpainting.py --image_folder /mnt/localssd/code/data/minibo/foreground --mask_folder /mnt/localssd/code/data/minibo/mask --output_folder /mnt/localssd/code/data/minibo/inpainted

python gpt4o-api.py --input_image_folder /mnt/localssd/code/data/minimam/inpainted --prompt_file_path ./system-prompts/image-caption.txt --output_file /mnt/localssd/code/data/minimam/inpainted.json
python gpt4o-api.py --input_image_folder /mnt/localssd/code/data/minibo/inpainted --prompt_file_path ./system-prompts/image-caption.txt --output_file /mnt/localssd/code/data/minibo/inpainted.json

```

### Compare two images based on reference image

```
python gpt4o-two-images.py --reference_folder /mnt/localssd/code/data/minibo/ --target_folder /mnt/localssd/code/YoChameleon/example_training_data/bo/laion --output_file /mnt/localssd/code/data/minibo/laion_based_on_reference.json
```

