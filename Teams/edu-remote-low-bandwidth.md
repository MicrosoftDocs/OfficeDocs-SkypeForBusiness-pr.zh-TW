---
title: 疑難排解 Teams 的低頻寬案例
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: 取得有關 Teams 中頻寬不足問題的會議和視訊問題的說明。 無論您是家長、授課者或 IT 管理員，您都可以選擇改善 Teams 的使用體驗。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f60095f20d62ed14b19d7c23493553efc39b872
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426810"
---
# <a name="troubleshoot-low-bandwidth-scenarios-for-teams"></a>疑難排解 Teams 的低頻寬案例

本文將為 IT 系統管理員提供在 Teams 中處理低頻寬問題的最佳做法。

許多網路元素可能會影響使用 Microsoft Teams 時的效能。

- 學校的低速網際網路連線。
- 一或多個學生的低速網際網路連線。
- 一天當中不時會因為某個區域的網路使用量而導致低頻寬的情形。
- 學校或學生的本機中斷，但會影響效能。
- 造成低頻寬問題的硬體問題。

> [!IMPORTANT]
> 閱讀 [Microsoft Teams 如何使用記憶體](teams-memory-usage-perf.md) 來限制裝置的資源。
>
>如需 Teams 網路指導方針，請參閱 [為 Microsoft Teams 準備貴組織的網路](prepare-network.md)。

## <a name="resolving-low-bandwidth-issues-for-it-admins"></a>解決 IT 系統管理員的低頻寬問題

有些問題可能只會在個別使用者層級以縮小焦點來解決。

如果許多使用者發生頻寬問題，或在使用者層級採取的動作沒有説明，則下一步就是整個學校的動作。

> [!NOTE]
> 您也可以閱讀 [體驗品質檢閱指南](quality-of-experience-review-guide.md)。 它不是 EDU 專用，但有寶貴的資訊。

### <a name="meetings-and-video"></a>會議與視訊

處理網路頻寬不足的相關會議問題時，請考慮下列動作。

#### <a name="meeting-video-policies"></a>會議視訊原則

Teams 會自動將會議品質調整為使用者偵測到的頻寬。 不過，您可以設定進一步的限制來保留頻寬。

您可以透過原則設定的一些限制包括：

- 完全關閉視訊，讓沒有人可以使用視訊。
- 限制每個使用者設定的媒體位元速率。

如需您應針對會議和視訊設定的更多原則，請參閱 [Teams 中的會議原則設定：音訊和視訊](meeting-policies-audio-and-video.md)。

#### <a name="screen-sharing-policies"></a>螢幕共用原則

在 Teams 中，使用者可以共用整個螢幕或個別視窗。

共用整個螢幕會使用比只共用視窗更多的頻寬。

- 限制使用者無法透過原則共用整個螢幕。
- 指示授課者只共用應用程式，而不是整個螢幕。

在 [Teams 中的會議原則設定：音訊和視訊](meeting-policies-audio-and-video.md)瞭解螢幕共用原則。

#### <a name="dial-in-number-for-meetings"></a>會議的撥入號碼

對於某些學生來說，撥入教室會話可能會比較容易。

- 提供 Teams 會議的撥入號碼，做為參加視訊會議的替代方案。

如需詳細資訊，請參閱 [在 Microsoft Teams 中設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="low-bandwidth-scenarios-as-an-educator"></a>身為老師的低頻寬案例

在下列情況下，讓授課者疑難排解頻寬問題可能是比 IT 動作更好的選擇：

- 這是間歇性的問題。
- 您可以在一天的特定時間預期發生問題。

如需授課者可採取的解決頻寬問題的步驟，請參閱 [在頻寬不足時使用 Teams 進行學校作業](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)。

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>身為家長或學生的低頻寬案例

頻寬問題有時會位在學生的側邊。

- 他們的住家可能無法存取高頻寬。
- 他們的直接區域中可能有許多人也會耗用頻寬。
- 可能有網際網路不穩定。

針對家長和學生，當 [頻寬偏低時，我們已在使用 Teams 進行學校作業](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) 中整理指導方針。
