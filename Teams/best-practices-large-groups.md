---
title: 在 Microsoft 團隊中管理大型團隊-最佳做法
ms.reviewer: abgupta
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 瞭解在 Microsoft 團隊中管理大型團隊以滿足貴組織的需求的最佳做法。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d939b4be4fcd5f3a1045f2f9adde750197b92f29
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638903"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>在 Microsoft 團隊中管理大型團隊-最佳做法
======================================================

Microsoft 團隊也相當高效，可促進含數十個成員的小型群組之間的通訊，以及含上千個成員的大型群組。 針對小組規模的更新[，查看小組的限制與規格](limits-specifications-teams.md)。 團隊規模增加會帶來獨特的管理與操作難題。 本文將說明建立及管理數千個成員組成的大型小組的最佳做法。

## <a name="value-of-large-teams"></a>大型團隊的價值

大型團隊在啟用下列共同作業案例時非常有用：

- **整個部門共同**作業：如果您的組織有多個部門（例如財務、運營、R&D 等），則您可以建立單一小組，其中包含特定部門中的所有成員。 現在，所有與部門相關的通訊都可以在這個小組中共用，這可協助成員進行立即接觸和參與。

- **員工資源群組中**的共同作業：組織通常會有大量的人員，這些人屬於不同的部門或公司群組。 舉例來說，您可以有一群人分享個人財務及投資的熱情。 在大型組織中，通常很難連接。 若要為這類群組開發社區，租使用者管理員可以建立大型小組，以成為任何人都可以加入並利用的公用公司範圍資源群組。 最終，這些社區會收集新的和現有成員都可以欣賞的資訊。

- **內部與外部成員之間**的共同作業：常見的產品通常會開發一個早期開發人員群組，讓他們積極嘗試新版產品發行並提供意見反應。 早期的使用方式開發與產品群組的關聯，以協助形成產品。 在這種情況下，租使用者管理員可以設定大型小組，其中包含內部產品群組和外部產品評估程式，以協助豐富的產品開發流程。 這些團隊也可以為一組選取的客戶提供客戶支援。

## <a name="create-teams-from-existing-groups"></a>從現有的群組建立團隊

使用連絡人群組、安全性群組或 Office 群組快速開始您的小組。 您可以匯入群組來製作小組，或從 Office 群組建立小組。

匯**入群組以製作小組**：當您將含有最多3500成員的群組匯入小組時，小組會自動計算群組中的成員總數。 這只是一次性的匯入作業，而且小組中的未來變更將不會自動更新。

**從大型 microsoft 365 群組建立小組**：當您從大型 microsoft 365 群組建立小組時，成員會自動成為 Microsoft 365 群組**和**小組的一部分。 在將來，當小組成員加入或離開 Microsoft 365 群組時，系統會自動在小組中新增或移除他們。

## <a name="create-channels-to-focus-discussions"></a>建立頻道來聚焦討論

您可以建立焦點頻道，以縮小群組討論的範圍。 請參閱[組織團隊的最佳做法](best-practices-organizing.md)。

## <a name="restrict-channel-creation"></a>限制頻道建立

如果有任何小組成員允許建立頻道，該小組就可以進行頻道蔓延。 小組擁有者應該針對 [**設定] > 成員許可權**中的成員關閉頻道建立、更新、刪除及還原。 請參閱[團隊和頻道的概覽](teams-channels-overview.md)。

![顯示 [管理員主控台設定] 索引標籤的 [成員許可權] 區段的螢幕圖像。](media/no-channel-creation.png "[管理員主控台設定] 索引標籤的 [成員許可權] 區段的螢幕圖像。[允許建立或刪除頻道的成員] 選項未核取。")

## <a name="add-favorite-channels"></a>新增最愛頻道

為了加速新的使用者參與與內容探索，您可以選取預設提供給使用者的最愛頻道。 在系統管理中心的 [**頻道**] 窗格中，核取 [**成員顯示**] 欄下的頻道。

![顯示系統管理主控台 [頻道] 窗格的螢幕圖像。](media/favorite-channels.png "顯示系統管理主控台 [頻道] 窗格的螢幕影像。已核取 [針對成員顯示] 的一些頻道。")

 如需詳細資訊，請參閱[建立您的第一份團隊和頻道](get-started-with-teams-create-your-first-teams-and-channels.md)。

## <a name="regulate-applications-and-bots-in-large-teams"></a>在大型團隊中調整應用程式和 bot

為了避免加入干擾應用程式或 bot，小組擁有者可以停用、新增、移除及上傳小組成員的 app 與連接器。 在系統管理中心的 [設定] 底下的 [ **> 成員許可權**] 底下，取消核取允許成員新增 app 或連接器的三個選項。

![顯示 [設定] 窗格的 [成員許可權] 區段的螢幕圖像。](media/disable-bots-connectors.png "顯示 [設定] 窗格的 [成員許可權] 區段的螢幕圖像。[允許成員新增應用程式或連接器] 選項未核取。")

請參閱[app、bot、& 連接器](deploy-apps-microsoft-teams-landing-page.md)。

## <a name="regulate-team-and-channel-mentions"></a>控制小組與頻道提及

小組和頻道提及可用來繪製整個小組對特定頻道文章的注意。 在文章中使用提及之後，就會傳送通知給數以千計的小組成員。 如果通知太頻繁，小組成員可能會遭到超載，而且可能會抱怨小組擁有者。 若要避免小組或頻道提及，請取消核取 [團隊**設定] > @mentions**窗格中的方塊，以關閉成員的小組和頻道提及。

![顯示 [設定] 窗格中 [時間提及] 區段的螢幕圖像。](media/no-at-mentions.png "顯示 [設定] 窗格中 [時間提及] 區段的螢幕圖像。未核取 [顯示] 和 [賦予成員對提及的存取權] 的選項。")

## <a name="consider-setting-up-moderation-in-your-channels"></a>請考量在您的頻道中設定仲裁

小組擁有者可以針對頻道開啟仲裁，以控制誰可以開始新的文章，以及回覆該頻道中的文章。 當您設定仲裁時，您可以選擇讓一或多個小組成員成為仲裁者。 小組擁有者預設為版主。 如需詳細資訊，請參閱[設定及管理通道裁決](manage-channel-moderation-in-teams.md)。

## <a name="related-topics"></a>相關主題

- [組織團隊的最佳做法](best-practices-organizing.md)
- [建立組織範圍的小組](create-an-org-wide-team.md)
