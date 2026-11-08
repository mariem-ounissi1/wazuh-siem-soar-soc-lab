# Plateforme SIEM/SOAR open source : détection, réponse automatisée et assistant IA

Projet de fin d'études du Master professionnel en Administration des systèmes de sécurité informatique et Cloud Computing .

## Contexte et objectif

Un analyste SOC passe l'essentiel de son temps à trier des alertes, les enrichir et décider quoi en faire. J'ai voulu voir jusqu'où on peut alléger ce travail avec des outils entièrement open source : détecter les attaques, réagir sans intervention humaine quand c'est possible, et aider l'analyste à comprendre une alerte plus vite.

## Ce que j'ai réalisé

- **Détection** : collecte et analyse des journaux de machines Windows et Linux avec Wazuh, supervision du trafic réseau avec Suricata, indexation dans OpenSearch.
- **Réponse automatique** : blocage de l'adresse IP de l'attaquant après une attaque par force brute, grâce à l'Active Response de Wazuh.
- **Orchestration (SOAR)** : des workflows Shuffle qui enrichissent chaque alerte (VirusTotal, MalwareBazaar, MITRE ATT&CK) et envoient une notification sur Slack ou Telegram.
- **Gestion des incidents** : ouverture et suivi des cas dans DFIR-IRIS.
- **Assistant IA local** : un outil en Python/Flask, basé sur un modèle Ollama, qui résume une alerte et suggère des pistes d'investigation. Il tourne en local, donc aucune donnée ne quitte le laboratoire.

## Scénarios testés

J'ai simulé plusieurs attaques depuis Kali Linux pour vérifier que la chaîne complète fonctionne :

- force brute SSH et RDP, détection puis blocage automatique de l'IP , grâce à l'Active Response de Wazuh.
- dépôt d'un fichier de test EICAR pour valider la détection de malware, puis suppression du fichier malveillant, grâce à l'Active Response de Wazuh.
- scan du réseau avec Nmap et prise de contrôle simulée avec Metasploit.

Les résultats, captures et analyses sont dans le rapport.

## Technologies

| Domaine | Outils |
|---|---|
| SIEM / détection | Wazuh, OpenSearch, Suricata |
| SOAR / incidents | Shuffle, DFIR-IRIS |
| IA | Python, Flask, Ollama |
| Infrastructure | Docker, VMware, AlmaLinux, Ubuntu, Windows Server |
| Tests d'attaque | Kali Linux, Nmap, Hydra, Metasploit |

## Rapport complet

L'installation, la configuration et les scénarios de test sont détaillés dans le rapport : [SIEM-SOAR-IA.pdf](SIEM-SOAR-IA.pdf)

## Précisions

Tout a été réalisé dans un laboratoire virtuel isolé, avec des machines créées uniquement pour ce projet. Les mots de passe visibles dans le rapport sont des identifiants de test, et les adresses réseau ont été masquées.

## Contact

**Mariem Ounissi**, jeune diplômée en cybersécurité, à la recherche d'un poste junior en SOC ou en administration de systèmes sécurisés.
[LinkedIn](https://linkedin.com/in/mariem-ounissi)
