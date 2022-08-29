---
title: Microsoft Teams 中的團隊和頻道概覽
author: MikePlumleyMSFT
ms.author: mikeplum
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: 了解應用於各種需求 (例如財務、活動規劃和銷售等) 的不同團隊、頻道和應用程式。
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
- okr_smb
- intro-overview
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28a816dee54d8f5ac2aead0deeb6aedf3f8076f7
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396924"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Microsoft Teams 中的團隊和頻道概覽

讓我們先來了解 Microsoft Teams 如何讓個別小組在商務案例之間自我組織及共同作業：

- **Teams** 是與組織內不同專案和結果有關的人員、內容和工具的集合。

    - Teams 可以建立為只有受邀使用者才可加入的形式。
    - Teams 也可以建立為公開形式，組織內的任何人都可以加入 (最多 10,000 個成員)。
    
    團隊設計的目的是聚集一群人，讓他們以密切合作的方式來完成工作。 專案型工作 (例如啟動產品、建立數位出貨室) 的團隊可以是動態且持續性的，以反映組織的內部結構 (例如部門和辦公室位置)。 團隊中的聊天、檔案和記事只會對團隊成員顯示。

- **頻道** 是小組內的專用區段，可依據特定主題、專案或訓練等適合小組的分類來讓交談保持在井然有序的狀態。 您在頻道中共用的檔案 (位於 [檔案] 索引標籤上) 會儲存在 SharePoint 中。 如需詳細資訊，請參閱 [SharePoint Online 和商務用 OneDrive 如何與 Teams 互動](SharePoint-OneDrive-interact.md)。

    - 頻道是指交談發生的位置，以及實際完成工作的位置。 頻道的開放對象可以是：所有小組成員 (標準頻道)、選定的小組成員 ([私人頻道](private-channels.md))，或小組內部和外部的選定人員 ([共用頻道](shared-channels.md))。
    - 頻道若以包含索引標籤、連接器和 Bot 的應用程式進行擴充，則其對於團隊成員的作用，將最具價值。如需深入了解，請參閱 [Teams 中的應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。
    
如需使用團隊和頻道的說明，請參閱[團隊和頻道](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)。

如需使用 Teams 相關聯限制的詳細資訊，請參閱 [Microsoft Teams 的限制和規格](/microsoftteams/limits-specifications-teams)。

## <a name="membership-roles-and-settings"></a>成員資格、角色和設定

**團隊成員資格**

為您的整個組織啟用 Teams 時，團隊擁有者可以邀請與貴組織中共同作業的任何員工加入其團隊。 Teams 可讓團隊擁有者根據姓名輕鬆地在組織中新增人員。 根據組織的設定，您可以將組織外部人員以共用頻道中的來賓或外部參與者身分新增至您的小組。 如需詳細資訊，請參閱 [Microsoft Teams 中的來賓存取](guest-access.md)。 

團隊擁有者也可以根據現有的 Microsoft 365 群組建立團隊。 對群組成員資格所做的任何變更都會自動與 Teams 同步。

**團隊角色**

Teams 中的兩個主要角色如下： 

- **團隊擁有者** - 建立團隊的人員。 小組擁有者可以在邀請人員加入小組時，或在人員加入小組之後的任何時間點，讓任何小組成員成為共同擁有者。 擁有多個團隊擁有者，表示您能將管理設定和成員資格的責任 (包括邀請) 由其他人分擔。
- **團隊成員** - 擁有者邀請加入其團隊的人員。

此外，如果已設定仲裁功能，則團隊擁有者和成員都可以有頻道的仲裁者功能。 仲裁者可在頻道中開始新的文章，並控制團隊成員是否可以回覆現有的頻道訊息。 團隊擁有者可以在頻道內指派仲裁者。 (頻道擁有者會預設為具有仲裁者功能。) 頻道內的仲裁者可以新增或移除該頻道中的其他仲裁者。 如需詳細資訊，請參閱[在 Microsoft Teams 中設定和管理頻道仲裁](manage-channel-moderation-in-teams.md)。

> [!NOTE]
> 當您新增團隊擁有者時，也會將團隊擁有者新增為成員，除非團隊是在 Teams 系統管理中心建立，或是團隊新增至新的或現有的 Microsoft 365 群組時。

**團隊設定** 

小組擁有者可以直接在 Teams 中管理整個小組的設定。設定包括能夠新增小組圖片、設定小組成員的權限，以用於建立標準、私人和共用頻道、新增索引標籤和連接器、對整個小組或頻道使用 @提及，以及使用 Gif、貼圖和 meme。

如果您是 Microsoft 365 中的 Teams 系統管理員，您可以在 Teams 系統管理中心中存取全系統的設定。 這些設定可以影響團隊擁有者可在其團隊設定底下看到的選項和預設值。 例如，您可以啟用預設的「一般」頻道，用於整個小組的公告、討論和資源，這將顯示在所有小組中。

根據預設，所有使用者都有建立團隊的權限。 若要修改此內容，請參閱[在 Teams 中指派角色和權限](assign-roles-permissions.md)。

為了讓使用者與 Teams 接觸而建立早期規劃活動的其中一個重點是，這可協助使用者思考並了解 Teams 可如何加強他們日常生活中的共同作業。 藉由與其他人交談，協助他們選取目前以零碎方式進行共同作業的商務案例。 透過相關索引標籤將他們聚集在頻道中，以協助他們完成工作。 Teams 最強的使用案例之一就是任何跨組織的程序。

> [!NOTE]
> 在 Teams 中建立新的小組或私人或共用頻道時，會自動在 SharePoint 中建立小組網站。 若要編輯此小組網站的網站描述或分類，請前往對應頻道的 [Microsoft Teams 中的設定](https://support.microsoft.com/office/bf39798f-90d2-44fb-a750-55fa05a56f1d)。
>
> 深入了解如何管理 [Microsoft Teams 連線的小組網站](/SharePoint/teams-connected-sites)。

這段影片示範檢視和管理使用者團隊成員資格的步驟。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53x1L?autoplay=false]

## <a name="channel-feature-comparison"></a>頻道功能比較

下表顯示每個頻道類型 Teams 功能的比較。

|功能|標準頻道|私人頻道|共用頻道|
|:-------|:---------------|:--------------|:-------------|
|您可以在未將人員新增至小組的情況下，將人員新增至頻道。|否|否|是|
|頻道成員資格可能受限於小組的子集。|否|是|是|
|頻道可以直接與其他小組共用。|否|否|是|
|頻道可以直接與其父小組共用。|不適用|否|是|
|來賓可以參與頻道。|是|是|否|
|外部參與者 (B2B 直接連結) 可以參與頻道。|否|否|是|
|審核|是|否|否|
|分組會議室|是|否|否|
|複製頻道的連結|是|否|否|
|每個頻道都有專屬的 SharePoint 網站。|否|是|是|
|排定的會議|是|否|是|
|Planner|是|否|否|
|Bot、連接器和訊息擴充功能|是|否|否|
|在班級團隊中支援|是|是|否|
|標籤|是|否|否|
|分析|是|是|否|

## <a name="org-wide-teams"></a>全組織團隊

如果您組織的使用者不到 10,000 人，您可以建立全組織團隊。 全組織團隊提供自動化方式，讓組織中的每個人都成為單一團隊的一部分來進行共同作業。 如需詳細資訊 (包括建立及管理組織內團隊的最佳做法)，請參閱[在 Microsoft Teams 中建立全組織團隊](create-an-org-wide-team.md)。

## <a name="next-steps"></a>後續步驟

讀取 [Teams 中的聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)，逐步完成您首次使用 Teams 時的重要決策清單。
