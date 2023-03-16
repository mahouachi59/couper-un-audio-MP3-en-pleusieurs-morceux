from pydub import AudioSegment

# Charger le fichier audio
audio = AudioSegment.from_file("mon_fichier_audio.mp3", format="mp3")

# Définir la durée de chaque partie en millisecondes
part_duration = 10000

# Diviser le fichier audio en parties
parts = [audio[i:i+part_duration] for i in range(0, len(audio), part_duration)]

# Enregistrer chaque partie dans un fichier séparé
for i, part in enumerate(parts):
    part.export(f"partie_{i}.mp3", format="mp3")
