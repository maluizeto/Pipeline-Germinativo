# Pipeline-Germinativo
## Reset do Drive 
### Antes de iniciar o pipeline, usamos esse código para limpar e reogarnizar o Drive.
'''python
from google.colab import drive
import os
if os.path.isdir('/content/drive'):
    try:
        drive.flush_and_unmount()
    except ValueError:
        pass # Drive not mounted, ignore error
    os.system('rm -rf /content/drive/*') # Remove any residual files

if not os.path.exists('/content/drive'):
    os.makedirs('/content/drive')
else:
    os.system('rm -rf /content/drive/*')

drive.mount('/content/drive', force_remount=True)
'''
