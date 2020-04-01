---
title: Microsoft Teams 教育版的低頻寬指導方針
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Microsoft Teams 教育版文章，有助於解決與低頻寬有關的會議和影片問題。 無論您身為家長、老師還是 IT 系統管理員，都有選項可改善 Teams 的使用體驗。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f34ea2e65906c648081a019d6acf8a3f8a5cd5
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43034067"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>協助 Teams 教育版的低頻寬情況

在使用 Microsoft Teams 時，有許多可能會影響效能的網路元素，而低頻寬正是可能會讓您覺得完全失控的其中一種情況。 請考慮下列事項：

- 學校的低速網際網路連線。
- 一或多個學生的低速網際網路連線。
- 一天當中不時會因為某個區域的網路使用量而導致低頻寬的情形。
- 不是學校和學生所引起的服務中斷而導致低頻寬期間，雖然如此，但仍影響到效能。
- 偽裝成低頻寬問題的非頻寬問題 (例如硬體問題)。

本文會針對各種 Teams 活動，提供當您遇到低頻寬問題時可以遵循的最佳做法。

> [!IMPORTANT]
> 這裡有 [Microsoft Teams 如何使用記憶體](teams-memory-usage-perf.md)的相關資訊，因為除了低頻寬問題外，您的裝置也可能遇到資源問題。 如果您要尋找 Microsoft Teams 的網路指導方針，請檢閱[針對 Microsoft Teams 準備組織的網路](prepare-network.md)。

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a>解決 IT 系統管理員的低頻寬問題

請務必牢記，身為 IT 系統管理員，雖然您有各式各樣能迅速解決問題的低頻寬問題解決方案，但使用前請先仔細思考，因為有些問題或許在更為限縮的老師或甚至是學生/家長層級就能夠解決。

簡言之，如果是眾多學生遇到低頻寬問題，那麼以 IT 系統管理員的角色來採取行動便很合理，同樣地，如果在學生/老師層級採取行動沒有用，則以 IT 系統管理員的角色來採取行動也很合理。

> [!NOTE]
> 如果您有空，[體驗品質的審查指南](quality-of-experience-review-guide.md)值得一讀 (這雖非教育版專用指南，但仍有寶貴資訊)。 這可讓有經驗的 IT 系統管理員深入了解其老師和學生所獲得的體驗。

### <a name="meetings-and-video"></a>會議與影片

低頻寬問題的主要焦點在會議，尤其是會議中播放的影片。 當 IT 系統管理員在處理學生或老師所報告，有關要在教育設定下獲得最佳會議體驗的問題時，應考慮以下某些動作。

#### <a name="meeting-policies"></a>會議原則

就會議而言，低頻寬情況最令人擔憂的其中一點是播放影片。 幸運的是，Teams 可自動針對所偵測到的頻寬來擴縮，不僅如此，身為 IT 系統管理員，您也可以在每一召集人和/或每一使用者層級設定原則選項，讓每個人都能根據其在給定時間所使用的頻寬，而獲得最佳使用體驗。

可透過原則來設定的部分內容包括：

- 完全停用影片，讓所有人都無法啟用影片。
- 媒體位元速率 (根據每位使用者來加以設定)。

若要深入了解您的選項，並逐步查看必須為會議和影片設定的具體原則，請參閱 [Teams 中的會議原則設定：音訊和影片](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video)，以取得詳細的逐步說明資訊。

#### <a name="screen-sharing-policies"></a>螢幕共用原則

在其他情況下，老師可能會與學生共用其整個螢幕，這個時候，共用範圍應限制在與所授課程有關的應用程式上。 如果不想讓老師個別做選擇，而是有其他更想要的方式，那麼您也可以透過原則來設定此限制。

若要了解有什麼好方法可以讓您透過原則設定來限制螢幕共用，請參閱 [Teams 中的會議原則設定：螢幕共用](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video)。

#### <a name="dial-in-number-for-meetings"></a>會議的撥入號碼

讓某些學生嘗試撥入某些教室工作階段可能會更方便。 您可以為 Teams 會議提供撥入號碼，讓想要發問的學生可以打電話進來而非參加視訊會議。

如需這方面的詳細資訊，請參閱[將電話號碼設定為包含在 Microsoft Teams 的邀請中](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="low-bandwidth-scenarios-as-an-educator"></a>身為老師的低頻寬案例

老師應該會覺得他們有能力採取某些步驟來解決低頻寬問題，而且在下列情況時，可能是比由 IT 系統管理員採取行動還要好的選擇：

- 如果問題間歇發生，或持續時間相對短暫。
- 如果您預料當天的特定時間會發生問題，或可以一定程度地預測到低頻寬期間。

如果有這些情況，您就可以採取某些動作。

如需詳細資訊，請參閱[在低頻寬時使用 Teams 來完成學校作業](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)。

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>身為家長或學生的低頻寬案例

也有一些情況是您應該主動與老師討論的，因為頻寬問題可能是出在學生這邊 (例如，大量學生能夠正常觀看影片課程，但少數學生卻會發生問題)。

希望許多家長有能力排解這些問題並不合理，而且低頻寬問題可能不是學生或家長能夠控制的 (其住家可能無法存取高頻寬、其附近可能有很多人使用頻寬而影響其可以採取的行動、網際網路可能不穩定等等)。

我們也將家長和學生的指導方針一起放在[在低頻寬時使用 Teams 來完成學校作業](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)一文內供您檢閱，如果遇到任何問題，則可以嘗試這些建議。
