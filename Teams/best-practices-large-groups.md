---
title: 在 Microsoft Teams 中管理大型團隊 - 最佳做法
ms.reviewer: abgupta
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 瞭解在 Microsoft Teams 中管理大型團隊的最佳做法，以符合貴組織的需求。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
ms.openlocfilehash: fddf4b5cf80c51977b2a57ceceac8a07e529c51f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199075"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>在 Microsoft Teams 中管理大型團隊 - 最佳做法

Microsoft Teams 在協助數十個成員的小型群組與擁有數千個成員的大型群組之間進行溝通時，同樣有效。 檢閱 [Teams 的限制和規格](limits-specifications-teams.md) ，以取得有關團隊大小的更新。 團隊規模增加會導致獨特的管理和營運挑戰。 本文將說明建立和管理由數千個成員組成的大型團隊的最佳做法。

## <a name="value-of-large-teams"></a>大型團隊的價值

大型團隊在啟用下列共同作業案例時非常有用：

- **全部門共同作業**：如果貴組織有多個部門，例如財務、營運、R&D 等，則您可以建立一個包含特定部門中所有成員的單一小組。 現在，與部門相關的所有通訊都可以在此小組中共用，方便成員立即連絡和互動。

- **在員工資源群組中** 共同作業：組織通常會有一大群共同興趣的人員，他們屬於不同的部門或工作群組。 例如，可能有一群人對個人財務和投資充滿熱情。 在大型組織中連線通常很困難。 若要開發這類群組的社群，租使用者管理員可以建立大型小組，做為全公司的公用資源群組，任何人都可以加入並善用該群組。 最後，這些社群會收集新成員和現有成員都能享用的資訊。

- **內部和外部成員之間的共同** 作業：熱門產品通常會開發一個由渴望嘗試新產品發行並提供意見反應的早期採用者社群。 早期採用者會與產品群組發展關聯，以協助重塑產品。 在這種情況下，租使用者系統管理員可以設定一個包含內部產品群組和外部產品評估員的大型團隊，以促進豐富的產品開發程式。 這些小組也可以為特定一組客戶提供客戶支援。

## <a name="create-teams-from-existing-groups"></a>從現有群組建立團隊

使用連絡人群組、安全性群組或 Office 群組快速啟動您的小組。 您可以匯入群組來建立團隊，或從 Office 群組建立團隊。

**匯入群組以建立團隊**：當您將最多 3，500 個成員的群組匯入 Teams 時，Teams 會自動計算群組中的成員總數。 這是一次性的匯入，未來在群組中的變更將不會在 Teams 中自動更新。

**從大型 Microsoft 365 群組建立團隊**：當您從大型 Microsoft 365 群組建立團隊時，成員會自動成為 Microsoft 365 群組 **和** 團隊的成員。 日後當團隊成員加入或離開 Microsoft 365 群組時，會自動從團隊中新增或移除他們。

## <a name="bulk-importexportremove-members-in-a-team"></a>大量匯入/匯出/移除小組中的成員

Azure 入口網站可讓使用者在 Microsoft 365 群組中大量匯入/匯出/移除成員。 如需詳細資訊，請參閱 [大量匯入群組成員](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)。

由於每個小組都由 Microsoft 365 群組支援，您可以使用Azure 入口網站，在對應到團隊的群組中執行這些作業。 成員作業會在 24 小時內反映在團隊中。

## <a name="create-channels-to-focus-discussions"></a>建立頻道來聚焦討論

您可以建立焦點頻道以縮小群組討論範圍。 請參閱 [組織團隊的最佳做法](best-practices-organizing.md)。

## <a name="restrict-channel-creation"></a>限制頻道建立

如果允許任何團隊成員建立頻道，則該團隊可以擁有頻道轉場。 團隊擁有者應該在 [ **設定] > [成員**] 許可權中關閉成員的通道建立、更新、刪除和還原。 請參閱 [團隊和頻道概觀](teams-channels-overview.md)。

![顯示 [系統管理主控台設定] 索引標籤 [成員許可權] 區段的螢幕影像。](media/no-channel-creation.png "系統管理主控台 [設定] 索引標籤中成員許可權區段的螢幕影像。未選取允許成員建立或刪除頻道選項。")

## <a name="add-favorite-channels"></a>新增最愛的頻道

為了加快新的使用者參與度和內容探索，您可以選取使用者預設可使用的最愛頻道。 在系統管理中心的 [ **頻道** ] 窗格中，核取 [ **顯示成員]** 欄底下的頻道。

![顯示系統管理主控台 [頻道] 窗格的螢幕影像。](media/favorite-channels.png "顯示系統管理主控台 [頻道] 窗格的螢幕影像。部分頻道已核取 [顯示成員]。")

 如需詳細資料，請參閱 [建立您的第一個團隊和頻道](get-started-with-teams-create-your-first-teams-and-channels.md) 。

## <a name="regulate-applications-and-bots-in-large-teams"></a>規範大型團隊中的應用程式和 Bot

為了避免造成應用程式或 Bot 分心，團隊擁有者可以針對團隊成員停用、新增、移除及上傳應用程式和連接器。 在 [ **設定>成員** 許可權] 下的系統管理中心，取消核取三個允許成員新增應用程式或連接器的選項。

![顯示 [設定] 窗格 [成員許可權] 區段的螢幕影像。](media/disable-bots-connectors.png "顯示 [設定] 窗格 [成員許可權] 區段的螢幕影像。未選取允許成員新增應用程式或連接器的選項。")

請參閱 [Teams 應用程式概觀](deploy-apps-microsoft-teams-landing-page.md)。

## <a name="regulate-team-and-channel-mentions"></a>規範團隊和頻道提及

團隊和頻道提及可用來吸引整個團隊對特定頻道文章的注意。 文章中使用提及後，就會傳送通知給數千個小組成員。 如果通知過於頻繁，小組成員可能會變得負荷過重，並且可能會向團隊擁有者抱怨。 若要防止團隊或頻道提及，請取消核取 [團隊設定] > @mentions窗格中的方塊，以關閉成員的團隊 **和** 頻道提及功能。

![顯示 [設定] 窗格 [提及] 區段的螢幕影像。](media/no-at-mentions.png "顯示 [設定] 窗格 [提及] 區段的螢幕影像。系統不會選取顯示及授與成員在提及時存取權的選項。")

## <a name="consider-setting-up-moderation-in-your-channels"></a>請考量在您的頻道中設定仲裁

小組擁有者可以針對頻道開啟仲裁，以控制誰可以開始新的文章，以及回覆該頻道中的文章。 當您設定仲裁時，您可以選擇讓一或多個小組成員成為仲裁者。 團隊擁有者預設為仲裁者。 如需詳細資訊，請參閱 [設定及管理頻道仲裁](manage-channel-moderation-in-teams.md)。

## <a name="related-topics"></a>相關主題

- [組織 Teams 的最佳做法](best-practices-organizing.md)
- [建立全組織團隊](create-an-org-wide-team.md)