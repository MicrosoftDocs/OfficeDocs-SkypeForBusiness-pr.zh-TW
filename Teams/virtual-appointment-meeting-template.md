---
title: Microsoft Teams 中的虛擬約會會議範本
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
searchScope:
- Microsoft Teams
audience: admin
description: 瞭解如何管理貴組織中 Teams 使用者的虛擬約會會議範本。
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0d93bb05a6456499ab1c0c16070149d8cdfd949
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767624"
---
# <a name="virtual-appointment-meeting-template-in-microsoft-teams"></a>Microsoft Teams 中的虛擬約會會議範本

![資訊圖示 ](media/info.png) **本文所述的部分功能需要 [Teams 進階版 (](teams-add-on-licensing/licensing-enhance-teams.md)預覽)**。

## <a name="overview"></a>概觀

虛擬約會範本是 Microsoft Teams 中的預設會議範本，您的使用者可以使用它來排程與客戶、客戶和組織外部其他人員的虛擬約會。 例如，使用它來排程並進行面試、指導會話、財務諮詢、虛擬購物體驗等等。

範本可讓您為會議召集人通常控制的會議設定指定值。 它可讓您彈性地套用預設設定並強制執行設定。 您可以選擇鎖定設定，讓會議召集人在使用範本時無法變更設定。

您可以使用此範本，針對 Teams 內排程的虛擬約會啟用一致的體驗，並協助強制執行合規性要求。

本文提供如何在 Teams 系統管理中心檢視和管理虛擬約會會議範本的概觀。

## <a name="view-or-change-virtual-appointment-meeting-template-settings"></a>檢視或變更虛擬約會會議範本設定

1. 在 Teams 系統管理中心的左側導覽中，移至 **[會議**  >  **會議] 範本**。
1. 選擇 **[虛擬約會**]，然後選取 [ **編輯]**。
1. 若要進行變更，請選取一個選項，然後設定您要的設定。 您可以針對每個選項定義下列設定：
    - **預設值**：使用範本時套用至虛擬約會的值。
    - **可見度**：選擇 **[隱藏** ] 或 **[顯示** ]，指定會議召集人是否可在 Teams 會議選項中看到該選項。
    - **鎖定狀態**：若要防止會議召集人變更您設定的值，請選擇 **[鎖定]**。 若要允許會議召集人變更您設定的值，請選擇 [ **解除鎖定]**。
1. 檢閱您的變更，然後選擇 [ **儲存]**。

## <a name="manage-the-virtual-appointment-meeting-template"></a>管理虛擬約會會議範本

您可以使用 Teams 系統管理中心的會議範本原則來控制組織中使用者可使用的會議範本。 根據預設，全域原則可讓使用者查看及使用所有會議範本，包括虛擬約會範本，以及您建立的任何自訂範本。

如果您想要讓貴組織中的特定使用者或使用者群組使用虛擬約會範本，您可以建立自訂會議範本原則，然後將它指派給這些使用者或群組。

若要深入瞭解，請參閱 [管理 Teams 中的會議範本](manage-meeting-templates.md)。

## <a name="user-experience"></a>使用者體驗

當貴組織中的使用者使用會議範本來排程虛擬約會時，組織外部人員 (外部來賓) 取得量身打造的會議邀請，其中包含 [以來賓身分 **加入約會** ] 按鈕及其他約會詳細資料。 他們可以使用此按鈕從任何裝置輕鬆加入，而不需要下載並安裝 Teams。

請記住，某些 Teams 會議選項可能不會套用至外部來賓或任何使用 [以來賓身分加入 **約會** ] 按鈕加入的人員。 來賓加入支援下列會議選項：

- **誰可以略過大廳**：[ **所有人** ] 設定可讓外部來賓略過大廳。
- **選擇共同召集人**
- **自動錄製**
- **允許會議聊天****：如果您想要** 在會議之前、期間和之後防止會議聊天，請設定為 [停用]。

貴組織內部的人員會收到會議邀請，而約會會出現在他們的 Teams 和 Outlook 行事曆中，他們可以輕鬆加入，就像加入任何其他 Teams 會議一樣。 所有 Teams 會議選項都適用于使用會議邀請中的 Teams 會議連結，或從 Teams 或 Outlook 行事曆加入的出席者。

若要深入瞭解如何使用虛擬約會會議範本和使用者體驗，請參閱 [使用 Teams 會議範本建立虛擬約會](https://support.microsoft.com/office/6a9e8cbb-c0ed-4598-851e-3b1750a4a747)。

## <a name="related-articles"></a>相關文章

- [Teams 中的自訂會議範本概觀](custom-meeting-templates-overview.md)
