---
title: 指派 Microsoft Teams 教育版授權
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 瞭解如何指派Microsoft Teams 教育版授權。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- admindeeplinkMAC
ms.openlocfilehash: e57780436167e3a872e78a717d12cd3acc35a6e9
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426800"
---
# <a name="assign-microsoft-teams-licenses-for-education"></a>指派 Microsoft Teams 教育版授權

本文適用于需要指派小組授權給教職員和學生的教育用 IT 系統管理員。

若要讓使用者準備好使用 Teams，您必須：

1. [在 Microsoft 365 系統管理中心 中為您的學校啟用 Microsoft Teams](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)。
2. 指派授權給使用者帳戶以存取 Microsoft 365 服務，包括 Teams。

## <a name="ways-to-assign-teams-licenses"></a>指派 Teams 授權的方式

您可以指派授權給使用者帳戶：

- Microsoft 365 系統管理中心中的個別或少數使用者。
- 使用 [PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) 或 [Active Directory 群組授權自動透過群組](/azure/active-directory/users-groups-roles/licensing-groups-assign)成員資格。

本文將逐步引導您瞭解如何在Microsoft 365 系統管理中心中指派授權。

在Microsoft 365 系統管理中心中，您可以針對下列任一項指派授權給使用者：

- 將產品授權指派給特定使用者 **的 [授權** ] 頁面。
- [ **作用中使用者]** 頁面，指派使用者授權給特定產品。

> [!NOTE]
> 您必須是全域系統管理員、計費系統管理員、授權系統管理員或使用者管理系統管理員。如需詳細資訊，請參閱[關於 Office 365 系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>在 [授權] 頁面上指派授權給使用者

在 **[授權]** 頁面上，您會看到您擁有訂閱的所有產品清單、每個產品的授權總數、已指派多少個授權，以及可用的授權數目。

1. 在 [系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)，移至 **[帳單**  >  [授權]](https://go.microsoft.com/fwlink/p/?linkid=842264)頁面。

2. 選取您要指派授權的產品。 Microsoft Teams 是學生 SKU 免費Microsoft 365 A1的一部分。

3. 選取 **[指派授權]**。

4. 在 **[將授權指派給使用者]** 窗格中，開始輸入名稱，這會產生名稱清單。

5. 從結果中選擇您要尋找的名稱，將它新增到清單中。 一次最多可以新增 20 個使用者。

6. 選取 **[開啟或關閉應用程式與服務]** 以指派或移除特定項目 (例如 Microsoft Teams) 的存取權。 請確認已選取 **[Microsoft Teams]** 和 **[Office 網頁版 (教育)]**。

7. 完成時，請選取 **[指派]**，然後選取 **[關閉]**。

### <a name="change-the-apps-and-services-a-user-has-access-to"></a>變更使用者有權存取的應用程式和服務

1. 選取包含使用者的列。

2. 在右窗格中，選取或取消選取您要授與存取權或移除存取權的應用程式與服務。

3. 完成時，請選取 **[儲存]**，然後選取 **[關閉]**。

## <a name="assign-licenses-to-users-on-the-active-users-page"></a>在 [作用中使用者] 頁面上指派授權給使用者

1. 在 [系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)，移至 [**使用者**  >  [作用中使用者]](https://go.microsoft.com/fwlink/p/?linkid=834822)頁面。

2. 選取您要指派授權的使用者名稱旁的圓圈。

3. 在頂端，選取 **[管理產品授權]**。

4. 在 **[管理產品授權]** 窗格中，選取 **[新增到現有產品授權指派]** > **[下一步]**。

5. 在 **[新增到現有產品]** 窗格中，針對您已選取要指派授權的使用者，將開關切換到 **[開啟]** 位置。 請確認已選取 **[Microsoft Teams]** 和 **[Office 網頁版 (教育)]**。

   根據預設，與這些授權相關的所有服務都會自動指派給使用者。 您可以限制使用者能使用的服務。 針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。

6. 在窗格底部，選取 **[新增**  >  **關閉]**。
