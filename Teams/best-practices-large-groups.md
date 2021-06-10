---
title: 管理大型團隊Microsoft Teams - 最佳做法
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 瞭解管理大型團隊的最佳作法Microsoft Teams以符合貴組織的需求。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fff84bd660eb19f01c6a7e3388f5289b09896401
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856342"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>管理大型團隊Microsoft Teams - 最佳做法

Microsoft Teams能促進與數十個成員和數千個成員的大型群組之間的溝通。 針對[小組大小更新Teams](limits-specifications-teams.md)限制和規格。 團隊規模增加會導致獨特的管理和營運挑戰。 本文將說明建立及管理由數千個成員組成的大型團隊的最佳作法。

## <a name="value-of-large-teams"></a>大型團隊的價值

大型團隊在啟用下列共同合作案例時非常實用：

- **全部門** 共同作業：如果貴組織有多個部門 ，例如財務、營運、R&D 等，則您可以建立一個包含特定部門中所有成員的小組。 現在，所有與部門相關的通訊都可以在這個小組中共用，方便成員立即聯繫和互動。

- **員工資源群組中的共同** 作業：組織通常有一大群具有共同興趣的人，他們屬於不同的部門或工作組。 舉個例說，可以有一群對個人財務與投資充滿熱忱的人。 在大型組織中通常難以聯繫。 若要為這類群組開發社群，租使用者系統管理員可以建立大型團隊，做為全公司的公用資源群組，任何人都可以加入並利用。 最後，這些社群會收集新成員和現有成員都可以享有的資訊。

- **內部和外部成員** 之間的共同合作：熱門產品通常會開發一個早期採用者社群，他們急迫嘗試新產品發行，並提供意見回饋。 早期採用者會與產品群組建立關係，協助塑造產品。 在這種情況下，租使用者系統管理員可以設定包含內部產品群組和外部產品評估員的大型小組，以協助豐富的產品開發程式。 這些團隊也可以為一組選取的客戶提供客戶支援。

## <a name="create-teams-from-existing-groups"></a>從現有的群組建立團隊

使用連絡人群組、安全性群組或Office群組來快速啟動您的小組。 您可以輸入群組來建立團隊，或從群組建立Office團隊。

將 **群組** 輸入成團隊：當您將最多 3，500 個成員的群組Teams，Teams會自動計算群組中的成員總數。 這是一次導入，群組中未來的變更將不會在 Teams。

**從大型群組建立** Microsoft 365：當您從大型群組Microsoft 365團隊時，成員會自動成為群組 **Microsoft 365團隊的** 一部分。 日後，當小組成員加入或離開Microsoft 365群組時，系統會自動新增或移除他們。

## <a name="bulk-importexportremove-members-in-a-team"></a>大量匯出/匯出/移除團隊中的成員

Azure 入口網站允許使用者大量匯出/匯出/移除群組Microsoft 365成員。 詳細資訊，請參閱 [大量導入群組成員](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)。

由於每個團隊都有一個Microsoft 365，您可以使用 Azure 入口網站，在對應該團隊的群組中執行這些作業。 成員作業將在 24 小時內反映在團隊中。

## <a name="create-channels-to-focus-discussions"></a>建立頻道來聚焦討論

您可以建立焦點頻道來縮小群組討論範圍。 請參閱 [組織團隊的最佳作法](best-practices-organizing.md)。

## <a name="restrict-channel-creation"></a>限制頻道建立

如果允許任何團隊成員建立頻道，該團隊可以擴大頻道。 團隊擁有者應在成員許可權中關閉成員頻道的建立、更新、刪除 **設定 >還原**。 請參閱 [團隊和頻道概觀](teams-channels-overview.md)。

![顯示系統管理主控台中成員許可權區段的螢幕設定畫面。](media/no-channel-creation.png "系統管理主控台中成員許可權區段的螢幕設定畫面。未取消勾選允許成員建立或刪除頻道選項。")

## <a name="add-favorite-channels"></a>新增我的最愛頻道

若要加快新的使用者互動和內容探索，您可以選取使用者預設可用的最愛頻道。 在 **系統管理中心的** 頻道窗格中，檢查顯示成員欄下的 **頻道** 。

![顯示系統管理主控台的頻道窗格的螢幕圖像。](media/favorite-channels.png "顯示系統管理主控台的頻道窗格的螢幕圖像。某些頻道會檢查為成員顯示。")

 請參閱 [建立您的第一個團隊和頻道以](get-started-with-teams-create-your-first-teams-and-channels.md) 瞭解詳細資料。

## <a name="regulate-applications-and-bots-in-large-teams"></a>在大型團隊中規範應用程式和 Bot

為了防止新增令人分心的應用程式或 Bot，團隊擁有者可以針對小組成員停用、新增、移除及上傳應用程式和連接器。 在系統管理 **中心設定 >**，取消勾選允許成員新增 App 或連接器的三個選項。

![顯示窗格之成員許可權區段的設定圖像。](media/disable-bots-connectors.png "顯示窗格之成員許可權區段的設定圖像。允許成員新增 App 或連接器的選項會取消勾選。")

請參閱 [應用程式、bot、&連接器](deploy-apps-microsoft-teams-landing-page.md)。

## <a name="regulate-team-and-channel-mentions"></a>規範團隊和頻道提及

小組和頻道提及可以用來吸引整個團隊對特定頻道文章的注意。 在文章使用提及後，通知會發送給數千名小組成員。 如果通知過於頻繁，則小組成員可能會超載，並可能會向團隊擁有者抱怨。 若要避免團隊或頻道提及，請取消勾選團隊或頻道窗格中的 **設定 > @mentions提及。**

![Screen image that shows the at Mentions section of the Settings pane.](media/no-at-mentions.png "顯示窗格的 <提及> 區段的設定圖像。未勾選顯示和給予成員提及存取權的選項。")

## <a name="consider-setting-up-moderation-in-your-channels"></a>請考量在您的頻道中設定仲裁

小組擁有者可以針對頻道開啟仲裁，以控制誰可以開始新的文章，以及回覆該頻道中的文章。 當您設定仲裁時，您可以選擇讓一或多個小組成員成為仲裁者。 團隊擁有者預設為仲裁者。 詳細資訊，請參閱[設定及管理通道管理。](manage-channel-moderation-in-teams.md)

## <a name="related-topics"></a>相關主題

- [組織活動的最佳Teams](best-practices-organizing.md)
- [建立全組織團隊](create-an-org-wide-team.md)