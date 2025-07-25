# Outer Wilds Mod Pack Template

Use this template to create Outer Wilds mod packs. Mod packs are mods with the `pack` tag that list other mods as dependencies.

> [!NOTE]
> Looking to create mods? [See the OWML Documentation](https://owml.outerwildsmods.com/guides/getting_started.html)

## Setup

First, create a new repository from this template using the "Use This Template" button on the top right.

![The Use This Template Button](https://github.com/user-attachments/assets/d73c8d3a-deb0-40a9-9bf3-7bb96240bfc8)

After creating the template repository, open `manifest.json` and click the pencil icon to edit it.

In this file you'll need to replace three strings with values specific to your mod.

- `author`: Your Name
- `name`: Human-readable name for the mod
- `uniqueName`: A unique name for the mod that can't be the same as any other mod. Convention is to format it `Author.Name`. For example a mod "Time Saver" by Bwc9876 would become `Bwc9876.TimeSaver`
 
After changing these value, commit your changes by clicking the green "Commit" button and confirming.

> [!TIP]
> You should change the README file of the mod to describe your mod and also change the repo description. The first image in your README will be used as the thumbnail for the mod, this image should be a 3:1 aspect ratio.

### Adding Mods

To add mods to your pack, first find the mod on [the mods website](https://outerwildsmods.com/mods).

On a given mod page, press the details link below the install button.

<img width="1010" height="491" alt="image" src="https://github.com/user-attachments/assets/8ac65541-9f4d-4a99-9a68-700ce4b1c94c" />

From the details modal, copy the name listed under "Unique Name" for the mod.

<img width="582" height="443" alt="image" src="https://github.com/user-attachments/assets/cafa327c-0620-4810-9778-9387abdd5872" />

With this unique name copied, edit your `manifest.json` file to include the mod's unique name in the `dependencies` array.

```json
{
  "dependencies": [
    "xen.NewHorizons",
    "JohnCorby.VanillaFix"
  ]
}
```

After adding all of your mods, commit the changes using the green button on the top right.

## Publishing

When you want to get your mod in the DB, start by going to the "Actions" tab of your repository and running the "Create Release" Workflow.

<img width="2193" height="660" alt="image" src="https://github.com/user-attachments/assets/1d8e1c4f-34ab-4c75-8166-002f4f219888" />

After the workflow finishes, check the "Releases" page of the repository, there should be a draft release there.

<img width="478" height="144" alt="image" src="https://github.com/user-attachments/assets/32440267-4f33-4b55-9553-89b2059c9b58" />

Click on the release, fill it out with your release description and click publish it.

After the release is published, use the [Add Mod Issue Template](https://github.com/ow-mods/ow-mod-db/issues/new?labels=add-mod&template=add-mod.yml&title=%5BYour+mod+name+here%5D) on the mod database to add the mod.

> [!IMPORTANT]
> Make sure to give your mod the `pack` tag when prompted for tags applying to the mod.

Create the issue and a database administrator will work to get the mod added.

## Updating

After making changes to your pack, **bump the version number in manifest.json** and re-run the "Create Release" workflow. A new release will be created that you can publish. After publishing the database will pick up on the change automatically.

> [!WARNING]
> If you don't bump the version in the `manifest.json` file the action will not create a release.




