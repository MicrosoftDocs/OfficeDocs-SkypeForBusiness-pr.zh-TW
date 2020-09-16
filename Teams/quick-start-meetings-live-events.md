---
title: 系統管理員快速入門 - Microsoft Teams 的會議和即時活動
ms.reviewer: ''
description: 快速上手 Microsoft Teams 的會議和即時活動。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a990b62e6479e44308f65920c4f49264b4a131a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814393"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a>系統管理員快速入門 - Microsoft Teams 的會議和即時活動

Microsoft Teams 有 2 個集會方式 - 會議和即時活動。 請使用此文章來快速推出和設定貴組織的會議和即時活動。 

 - Teams 的**會議**包括音訊、視訊，且畫面可共用人數最多可達 300 人。 這些是在 Teams 中共同作業的重要方法之一。 而且，您不必一定要具備組織的成員資格 (或甚至不需要 Teams 帳戶！) 才能加入 Teams 會議，只要查看邀請中有關撥入會議的指示即可。 

 - **即時活動**是 Teams 會議的延伸，可讓您排程並產生活動，向大量線上觀眾串流播放，最多可讓 10,000 人參與。 如果您的會議參與人數會超過 300 人，請使用即時活動。
<br><br>**附註：** 針對政府用 Teams (GCC、GCC、DoD)，其限制仍為 250。 當政府用雲端限制從 250 增加至 300，我們就會更新本文章。
## <a name="get-licenses-for-meetings-and-live-events"></a>取得會議和即時活動的授權

任何人都可以免費參加 Teams 會議或公開即時活動，不需要授權。 出席者按一下 Teams 或會議邀請中的 [加入]**** 就能加入 Teams 會議。 會議的音訊是 Teams 會議的一部分，但是如果您希望人員能夠以電話撥入會議，則您必須提供撥入號碼。 

若是召集、排程和舉辦會議或即時活動的人員，這些人員需要下表列出的 Microsoft 365 或 Office 365 授權之一。 如果您已經在使用 Teams，您可能已經擁有召集和舉辦會議和即時活動所需的授權。 

:::image type="content" source="media/quick-start-meetings-live-events-image1.png" alt-text="Teams 會議和即時活動所需授權的表格":::

> <sup>1</sup>  會議召集人必須擁有[音訊會議附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)才能傳送內含電話撥入式會議的邀請。
>
> <sup>2</sup>  若是撥出至[**用下列電話號碼連絡我**號碼](set-up-the-call-me-feature-for-your-users.md)的會議，召集人必須擁有 E5 或[音訊會議附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。 [撥號對應表](what-are-dial-plans.md)可能也在必要項目之列。 

 > [!Note]
 > 如需詳細資料，請參閱[依平台的團隊功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

若要深入瞭解授權，請參閱 [Microsoft Teams 服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。 

## <a name="make-sure-your-networks-ready"></a>確定網路已準備就緒

如果您的網路在推出 Microsoft 365 或 Office 365 時已準備就緒，則表示您已完成所有準備。 無論如何，尤其是您要快速推出 Teams 做為您支援**遠端工作者**的第一個 Office 365 工作負載的話，請參閱[針對 Teams 準備組織的網路](prepare-network.md)，確保您已準備就緒。

## <a name="meetings-and-conferencing"></a>會議和召集會議

- 身為系統管理員，您要設定每個人的[會議設定](meeting-settings-in-teams.md)。 接著，您可以使用[會議原則](meeting-policies-in-teams.md)控制使用者可以使用 (和不可以使用) 哪些會議功能。 

- 若要了解如何管理會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

- 如果使用者是 Teams 會議的新手，請與新手們共用[管理會議](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4)訓練。 請查看由講師帶領的線上課程，[透過 Teams 進行有效會議](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings)。

- 若要深入了解管理會議的選項，請參閱[變更團隊會議的參與者設定](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)。

- 別忘了[管理使用者的裝置](device-management.md) - 電話、耳機、相機。 若要取得有關經過 Teams 認證的裝置最新資訊，請移至 [Teams 裝置](https://office.com/teamsdevices)。

## <a name="live-events"></a>即時活動

- 就像會議一樣，您身為系統管理員，您要針對每個人[設定即時活動](teams-live-events/configure-teams-live-events.md)。 然後設定 (和指派) [即時事件原則](teams-live-events/set-up-for-teams-live-events.md)，控制使用者可以執行 (和不可以執行) 的動作。

- 請確認您的即時活動製作人和召集人受過訓練，也就是將他們送去參加[開始使用即時活動](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a)課程。

- 如果您剛開始使用即時活動，請參閱[什麼是 Teams 即時活動？](teams-live-events/what-are-teams-live-events.md)和 [Teams 即時活動的方案](teams-live-events/plan-for-teams-live-events.md)。

## <a name="related-topics"></a>相關主題

[Teams 的會議和召集會議](deploy-meetings-microsoft-teams-landing-page.md)

[Teams 的音訊會議](deploy-audio-conferencing-teams-landing-page.md)

[Teams 的即時活動](teams-live-events/what-are-teams-live-events.md)

[Teams 的限制和規格](limits-specifications-teams.md)

[Microsoft 技術社群：Microsoft 365 中的即時活動](https://resources.techcommunity.microsoft.com/live-events/)
