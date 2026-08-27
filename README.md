# Cortex Studio

<p align="center">
  <img src="assets/images/cortex-studio-logo.svg" alt="Logo Cortex Studio" width="180" />
</p>

Cortex Studio est un éditeur de code desktop pour macOS, Linux et Windows. Il réunit l’édition de code, la navigation dans les projets, le terminal, Git, les serveurs de langage, le débogage, les extensions et les outils d’intelligence artificielle dans un environnement unique.

Le projet est **créé et initié par Abdoulaye Coumbassa**. Son objectif est de proposer une expérience de développement directe, performante et adaptée aux personnes qui veulent écrire, comprendre, tester et améliorer leur code depuis un seul espace de travail.

## Ce que Cortex Studio apporte

| Domaine | Expérience proposée |
|---|---|
| Édition | Écrire et modifier du code avec coloration syntaxique, navigation, multi-buffer et assistance du langage. |
| Projets | Ouvrir des dossiers, organiser plusieurs espaces de travail et retrouver rapidement fichiers, symboles et actions. |
| Terminal | Exécuter les commandes du projet dans le terminal intégré et suivre les processus directement depuis l’éditeur. |
| Git | Consulter les changements, travailler avec des branches et des worktrees, examiner les diffs et préparer les commits. |
| Langages | Utiliser les serveurs de langage, le formatage, les diagnostics, les références et les refactorings disponibles. |
| Débogage | Lancer des sessions de débogage et suivre les erreurs au plus près du code concerné. |
| Extensions | Étendre l’environnement avec des langages, thèmes, outils et intégrations supplémentaires. |
| Intelligence artificielle | Utiliser Cortex AI dans l’éditeur existant pour comprendre le code, proposer des changements et travailler dans le projet sélectionné. |

## Cortex AI

**Cortex AI** est l’intégration agentique de Cortex Studio. Elle utilise le système d’agents externes et le protocole ACP déjà présents dans l’éditeur pour afficher les conversations, les demandes de fichiers, les commandes du terminal, les permissions et la revue des diffs dans les composants existants.

Le runtime technique ACP utilisé par Cortex AI est OpenHands. Il reste accessible avec la commande officielle `uvx openhands acp`, tandis que son identité visible dans Cortex Studio est **Cortex AI**. Cette séparation permet de conserver la compatibilité technique et de présenter une identité produit cohérente.

Pour activer Cortex AI, ajoutez cette configuration dans le fichier de réglages :

```jsonc
{
  "agent_servers": {
    "Cortex AI": {
      "type": "custom",
      "command": "uvx",
      "args": ["openhands", "acp"],
      "env": {}
    }
  }
}
```

Pour protéger le projet, utilisez Cortex AI dans un workspace dédié, un Dev Container ou un environnement distant pris en charge par l’éditeur. Les actions sur les fichiers, le terminal et les ressources sensibles doivent rester soumises aux permissions existantes et à la revue des changements.

## Installation

Cortex Studio est prévu pour macOS, Linux et Windows. Les instructions de développement et de compilation sont disponibles ici :

- [Compiler Cortex Studio pour macOS](./docs/src/development/macos.md)
- [Compiler Cortex Studio pour Linux](./docs/src/development/linux.md)
- [Compiler Cortex Studio pour Windows](./docs/src/development/windows.md)

Les instructions relatives aux agents externes et à Cortex AI sont disponibles dans [la documentation des agents](./docs/src/ai/external-agents.md).

## Développement du projet

Avant de contribuer, lisez [CONTRIBUTING.md](./CONTRIBUTING.md), installez les dépendances nécessaires à votre plateforme et vérifiez les changements avec les outils du projet.

Chaque modification importante doit rester ciblée, être examinée dans son diff, être validée par les tests disponibles et être publiée dans une branche dédiée avant toute fusion.

## Principes du projet

Cortex Studio privilégie la rapidité d’ouverture, la réactivité de l’édition, la clarté des changements et le contrôle de l’utilisateur. Les fonctions lourdes doivent être activées à la demande. Les assistants agentiques doivent afficher leurs actions, respecter les permissions du workspace et permettre l’arrêt immédiat d’une session.

Aucun agent ne doit modifier silencieusement un fichier sensible, exécuter une action destructive ou sortir du workspace autorisé sans une règle explicite et vérifiable.

## Licence et attributions

Le code source est distribué principalement sous licence GPL-3.0-or-later, avec des composants Apache-2.0 lorsqu’ils sont identifiés comme tels. Les licences des dépendances et les notices d’attribution doivent être conservées et vérifiées avant chaque distribution.

Cortex Studio et Cortex AI sont les identités utilisées pour ce projet. Les composants et runtimes open source intégrés conservent leurs notices, leurs licences et leurs attributions respectives.

## Créateur du projet

**Abdoulaye Coumbassa**

Créateur et initiateur de l’identité Cortex Studio, du rebranding et de l’intégration Cortex AI.
