---
title: Microsoft Teams 中的公開預覽
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about the public preview in Microsoft Teams. Try out new features and provide feedback.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: ffdd34d8a36726d96bc44ae766e91ca6ae77280b
ms.sourcegitcommit: b535a70df5bc842f597889582df3eb86371f8139
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2022
ms.locfileid: "68869584"
---
# <a name="microsoft-teams-public-preview"></a>Microsoft Teams 公開預覽

> [!NOTE] 
> 預覽中包含的功能可能不完整，且在公開發行之前可能會變更。 提供預覽版僅針對評估和探索目的。 Office 365 政府社群雲端 (GCC) 不支援預覽功能。

Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.

如需 Teams 公開預覽中可用專案的清單，請流覽[Microsoft Teams 公開預覽技術資訊](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)、[Teams 管理員功能的版本資訊](/OfficeUpdates/teams-admin)，以及[Office 目前通道的版本資訊 (預覽) ](/officeupdates/current-channel-preview)。

## <a name="set-the-update-policy"></a>設定更新原則

Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy. Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app. You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users. The policy needs to be assigned to specific users because it doesn't over-write the global policy.

1. 登入 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com/)。

2. 選取 **[Teams]** > **[Teams 更新原則]**。

1. 選取 **新增** 以建立新原則，或選取現有原則以開啟 **更新原則**。

2. 為更新原則命名，新增描述，然後選取 **[顯示預覽功能]** 的設定。

   -   **追蹤 Office Preview** (預設)
       - 這個新的預設選項會自動為註冊 Office 目前通道 (預覽) 的任何使用者啟用 Microsoft Teams 公開預覽功能。 
       - 使用者不需要執行其他動作。
   -   **Enabled**
       - 無論使用者是否已註冊 Office 目前通道 (預覽)，此選項都會啟用 Microsoft Teams 公開預覽。 
       - 使用者也必須在 Teams 應用程式中選擇加入 Microsoft Teams 公開預覽。

   > [!NOTE]  
   > 對於不在 **目前通道 (預覽)** 中的 Microsoft Teams 公開預覽的現有使用者，IT 系統管理員需要從預設的 **追蹤 Office Preview** 切換到 **啟用**。
 
   - **未啟用** 
     - 終端使用者將無法使用 Microsoft Teams 公開預覽功能。

    ![顯示預覽設定對話方塊。](media/public-preview-policy.png)  

您也可以使用 PowerShell `Set-CsTeamsUpdateManagementPolicy` cmdlet 和 `-AllowPublicPreview` 參數設定原則。

## <a name="enable-public-preview"></a>啟用公開預覽

若要在桌面或 Web 用戶端上啟用公開預覽，您必須完成下列工作：

1. 選取設定檔左側的三個點以顯示 Teams 功能表。
2. 選取 **[關於]** > **[公開預覽]**。
3. 選取 [切換至公開預覽]。

> [!NOTE]  
> 此選項僅在 **顯示預覽功能** 設定為 **已啟用** 時可供使用。

### <a name="public-preview-for-microsoft-teams-rooms-on-windows"></a>Windows 上的 Microsoft Teams 會議室公開預覽

公開預覽預設為關閉。 開啟公開預覽時，使用者端可以存取 Teams 會議室公開預覽中的功能。 若要開啟公開預覽，請新增 ```<EnablePublicPreview>True</EnablePublicPreview>``` 至您的 XML 設定檔。

我們建議註冊 5-10 部裝置以公開預覽。 

所有公開預覽功能都會在 [Microsoft Teams 公開預覽 - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)

## <a name="teams-now-follows-office-preview-users"></a>Teams 現在會追蹤 Office Preview 使用者

如果使用者位於 Windows 與 Mac 上 Office 365 用戶端的目前通道 (預覽)，**追蹤 Office Preview** 的新全域原則預設值就會自動讓使用者位於 Teams 的公開預覽通道中。

Microsoft Office 將繼續從目前通道 (預覽) 接收更新，而 Teams 用戶端將會透過公開預覽通道接收更新。 此原則不會根據 Teams 通道去切換 Office 通道。 

**如何保留您目前未使用 Office 目前通道 (預覽) 的現有 Teams 預覽使用者？**

對於您已允許加入或退出 Microsoft Teams 公開預覽的現有使用者，以及想要維持其目前形式設定的現有使用者，您必須從新的預設值 **追蹤 Office Preview** 切換到 **已啟用** (請參閱 [更新原則](#set-the-update-policy))

**如何退出此設定？**

您可以停用 Teams 系統管理中心的設定，從 **追蹤 Office Preview** 到 **未啟用** (請參閱 [設定更新原則](#set-the-update-policy))

## <a name="related-topics"></a>相關主題

[公開開發人員預覽](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
