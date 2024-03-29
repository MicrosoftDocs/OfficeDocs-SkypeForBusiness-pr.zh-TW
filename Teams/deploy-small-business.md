---
title: 在小型企業中設定 Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 在您的小型企業中設定 Teams，讓使用者能夠使用聊天和檔案共用進行共同作業、設定與參加小型和大型會議，以及透過影片和語音進行交談。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 94c03224f25f1cd72c7e283411b0b1de6c38580e
ms.sourcegitcommit: 2dab123ad74fcad4db5390e9b745f72497a05882
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2022
ms.locfileid: "68560253"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>在小型企業中設定 Microsoft Teams

有許多方法可以自訂 Teams。 下列各章節將說明如何設定每個 Teams 工作負載：**聊天、團隊和頻道**；**會議與召集會議**；和 **語音解決方案**。 您對每個工作負載的順序設定由您決定。 雖然我們建議您先設定聊天、Teams 和頻道工作負載，但您可以先從會議和研討會，或甚至是雲端語音開始。 您可以自行選擇。

> [!NOTE]
> If you haven't done so already, we strongly suggest that you begin your Teams deployment with a pilot. A pilot will allow you and a few early adopters to get familiar with Teams and its features before your planning and eventual roll out. For more information about how to start your pilot, check out [Get started with Microsoft Teams](get-started-with-teams-quick-start.md).

在您廣泛使用 Teams 之前，請先檢閱 [確認您已準備就緒](get-started-with-teams-quick-start.md#make-sure-youre-ready) 中的項目，確認貴組織已準備就緒。

跳至您感興趣的節：

- [工作負載](#workloads)
  - [聊天、團隊和頻道](#chat-teams-and-channels)
  - [會議和研討會](#meetings-and-conferencing)
  - [含通話方案的 Teams 電話](#teams-phone-with-calling-plan)
- [部署用戶端](#deploy-clients)
- [訓練](#training)

## <a name="workloads"></a>工作負載
### <a name="chat-teams-and-channels"></a>聊天、團隊和頻道

聊天、團隊和頻道是 Teams 的基礎。 **聊天** 可讓一或多個使用者彼此交談、共用檔案，以及私下開會。 **Teams**，讓貴組織所有人或只有團隊中的人員可以看到，讓適當的人員無論工作或場合進行共同合作，無論是長時間執行的專案或規劃生日派對。 團隊中的 **頻道** 可以區隔主題、專案、部門或其他任何對您的團隊有意義的項目。 如需聊天、團隊和頻道的詳細資訊，請參閱 [團隊和頻道概觀](teams-channels-overview.md)。

> [!TIP]
> 在 Microsoft Learn 上完成 [管理 Microsoft Teams](/training/modules/m365-teams-collab-manage-teams/) 模組，以瞭解如何管理團隊角色、存取權限與訊息傳遞原則。

當您考慮推出團隊和頻道時，您必須決定誰應該可以建立團隊和頻道、組織外部的來賓是否可以存取它們等等。 文章 [Microsoft Teams 中的聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md) 提供許多有關聊天、團隊和頻道規劃的資訊，不過，以下是該文章中您應該思考的一些重點。 若您想要更多相關資訊，請選取該決策。

| 決策 | 描述 |
|--|--|
| [誰應該當 Teams 系統管理員？](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | 系統管理員角色可用於將特定權限授予您想要由誰管理 Teams 的人員。 小型企業可能不需要這些額外的角色，因為同一個人可能需負責 Teams 的各個層面。 稍後您隨時都可以新增或移除系統管理員。<br><br>[使用 Microsoft Teams 系統管理員角色來管理 Teams](using-admin-roles.md) |
| [誰應該是 Teams 擁有者和成員？](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | Teams 擁有者可控制誰可以存取團隊及其頻道。 他們可以決定團隊或頻道是 (對組織) 公開，或私人，也可以設定原則 (如頻道是否應該受到管理)。 成員可以存取團隊及其頻道 (除非該頻道設為私人頻道，且該成員並非此頻道的成員)，而且可以被指定為仲裁者。<br><br>[在 Microsoft Teams 中指派 Teams 擁有者和成員](assign-roles-permissions.md) |
| [應啟用來賓存取嗎？](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |來賓存取可讓貴組織中的人員邀請組織外部人員存取您的小組和頻道。 來賓存取通常用於與貴組織外部且與貴組織人員沒有正式關係的人員進行共同合作。 例如，您可以邀請專案規劃人員暫時進行某一專案。<br>來賓存取與外部存取不同。 來賓存取會邀請特定人員存取與貴組織人員的互動。  <br>來賓存取依預設為 **關閉**。 <br><br>[開啟或關閉 Microsoft Teams 的來賓存取](set-up-guests.md)  |

您不需要為使用者執行其他動作，使用者即可開始使用聊天、團隊和頻道。 不過，有許多選項可用來控制 Teams 的使用方式。 您可以現在變更，或等到您看到人員如何使用 Teams。 如需詳細資訊，請查看下列文章：

- [管理 Teams 中的訊息原則](messaging-policies-in-teams.md)
- [Teams 設定](enable-features-office-365.md#teams-settings)

### <a name="meetings-and-conferencing"></a>會議和研討會

會議和會議和研討會可讓貴組織的人員彼此以及與組織外部的人員開會。 擁有 Teams 或商務用 Skype 用戶端的任何人都可以受邀加入 **會議**。 使用裝置中的麥克風、相機和螢幕可讓參與者無需使用電話便能加入交談。 參與者可以使用電腦或行動裝置與其他參與者聊天、進行語音通話，以及分享影片和應用程式。

**音訊會議** 可讓參與者透過撥打會議電話號碼並輸入會議識別碼使用一般電話來加入會議。 當參與者沒有良好的網路連線、會議為僅供語音使用，或某些不允許參與者透過 Teams 用戶端加入會議的情況時，音訊會議便非常有用。

> [!TIP]
> 完成 Microsoft Learn 上的 [使用 Microsoft Teams 來管理會議、召集會議與活動](/training/modules/m365-teams-collab-manage-meetings) 模組，以更加熟悉會議與活動。

Teams 中的會議依預設為啟用狀態，不過，您可以控制召集人和參與者的會議體驗。 您也可以設定會議之前和會議期間，允許和不允許人員執行哪些工作。 如需詳細資訊，請參閱下列文章：

- [系統管理員快速入門 - Microsoft Teams 的會議和即時活動](quick-start-meetings-live-events.md)

### <a name="teams-phone-with-calling-plan"></a>含通話方案的 Teams 電話

含通話方案的 Microsoft 365 Teams 電話適用於使用者少於 300 位的企業，提供您辦公室電話系統的所有功能。 Teams 電話包括語音信箱、來電顯示、電話系統功能表、免付費電話號碼等等，您不需要管理複雜且昂貴的內部部署電話系統。

有關適用於中小型企業的 Teams 電話 (含通話方案) 詳細資訊，請參閱 [Teams 電話中小型企業指南](/microsoftteams/business-voice/whats-business-voice)。

## <a name="deploy-clients"></a>部署用戶端

When you're ready for your users to start using Teams, they can install the Teams client on their Windows, Mac, or Linux PC, or on their Android or iOS device. Users can download the Teams client directly from <https://teams.microsoft.com/downloads>.

確定將使用 Teams 的每個人都擁有 Teams 授權。 如需指派 Teams 授權的詳細資訊，請參閱 [管理使用者對 Teams 的存取權](user-access.md#using-the-microsoft-365-admin-center)。

> [!TIP]
> 完成 Microsoft Learn 上的 [部署 Microsoft Teams 用戶端](/training/modules/m365-teams-collab-deploy-clients/) 模組，以取得規劃 Teams 用戶端部署的建議。

如果貴組織使用 Microsoft Endpoint Configuration Manager、群組原則或協力廠商分配機制，將軟體部署到使用者的電腦上，請參閱 [使用 Microsoft Endpoint Configuration Manager 來安裝 Microsoft Teams](msi-deployment.md)。

如果您想要部署 Teams 用戶端的詳細資訊，請參閱 [取得 Microsoft Teams 用戶端](get-clients.md)。

## <a name="training"></a>訓練

若要瞭解如何訓練使用者使用 Teams，請參閱 [Microsoft Teams 訓練](training-microsoft-teams-landing-page.md)。
