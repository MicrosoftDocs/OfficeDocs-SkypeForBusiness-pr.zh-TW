---
title: 適用於 Microsoft Teams 教育版管理員的資源：指派教育版 Teams 授權
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams 教育版的授權逐步解說。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: e51d472bbf3310b03fea6344b354fc307c8ce08a
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587372"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a>指派 Microsoft Teams 教育版授權

Microsoft Teams 是將交談、內容和應用程式集中在同一個位置的數位中心。 因為它是在 Office 365 的基礎上建立，學校可以與他們熟悉的 Office 應用程式和服務整合。 您的機構可以使用 Microsoft Teams 建立共同作業教室、在專業學習社群中交流，以及與學校教職員溝通，這些都來自 Office 365 教育版的單一體驗。

若要開始使用，IT 系統管理員必須使用 Microsoft 365 系統管理中心[為您的學校啟用 Microsoft Teams](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)。
完成之後，您必須將授權指派給使用者帳戶，您的教職員、員工和學生才能存取 Office 365 服務，例如 Microsoft Teams。

您可以採用個別方式或透過群組成員資格，將授權指派給使用者帳戶。 本文將逐步引導您瞭解如何透過 Microsoft 365 系統管理中心，將 Office 365 授權指派給個別或一小部分的使用者帳戶。 若要透過群組成員資格自動指派授權，請參閱我們其中一篇支援文章：

- [Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [Active Directory 中的群組型授權](/azure/active-directory/users-groups-roles/licensing-groups-assign)

您可以在 [授權] 頁面或 [作用中使用者] 頁面上將授權指派給使用者。 所使用的方法取決於您要指派產品授權給特定使用者，還是要將使用者授權指派給特定產品。

> [!NOTE]
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心]** 開關將它開啟。

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>在 [授權] 頁面上指派授權給使用者

> [!NOTE]
> 您必須是全域系統管理員、計費系統管理員、授權系統管理員或使用者管理系統管理員。如需詳細資訊，請參閱[關於 Office 365 系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。

使用 **[授權]** 頁面指派授權時，您可以指派特定產品的授權給最多 20 位使用者。 在 **[授權]** 頁面上，您會看到您訂閱的所有產品清單，以及每個產品的授權總數、已獲指派多少個授權，以及有多少個授權可供使用。

1. 在系統管理中心中，前往 **[帳單]** > [[授權]](https://go.microsoft.com/fwlink/p/?linkid=842264) 頁面。

   ![帳單視窗和功能表選項的螢幕擷取畫面。](media/EDU-Lic-Billing-License.png)
2. 選取您要指派授權的產品。 Microsoft Teams 是免費版學生用 Office 365 A1 SKU 的一部分。

   ![[授權] 頁面的螢幕擷取畫面，其中包含可指派授權的產品。](media/EDU-Lic-Licenses-Products.png)
3. 選取 **[指派授權]**。

   ![頁面的 [使用者] 區段的螢幕擷取畫面，[指派授權] 選項前面有加號。](media/EDU-Lic-Assign-Licenses.png)
4. 在 **[將授權指派給使用者]** 窗格中，開始輸入名稱，這會產生名稱清單。 從結果中選擇您要尋找的名稱，將它新增到清單中。 一次最多可以新增 20 個使用者。

   ![[將授權指派給使用者] 頁面的螢幕擷取畫面，當中輸入了部分名稱，並顯示該部分名稱的搜尋結果。](media/EDU-Lic-Assign-Licenses-Users.png)
5. 選取 **[開啟或關閉應用程式與服務]** 以指派或移除特定項目 (例如 Microsoft Teams) 的存取權。 請確認已選取 **[Microsoft Teams]** 和 **[Office 網頁版 (教育)]**。
6. 完成時，請選取 **[指派]**，然後選取 **[關閉]**。

變更使用者可以存取的應用程式與服務：

1. 選取包含使用者的列。
1. 在右窗格中，選取或取消選取您要授與存取權或移除存取權的應用程式與服務。
1. 完成時，請選取 **[儲存]**，然後選取 **[關閉]**。

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a>在 [作用中使用者] 頁面上將授權指派給個別或多個使用者

1. 在系統管理中心中，移至 **[使用者]** > [[作用中使用者]](https://go.microsoft.com/fwlink/p/?linkid=834822) 頁面。

   ![Microsoft O365 系統管理中心中 [作用中使用者] 功能表選項的螢幕擷取畫面。](media/EDU-Lic-Active-Users.png)
2. 選取您要指派授權的使用者名稱旁的圓圈。

   ![[作用中使用者] 頁面的螢幕擷取畫面，該頁面上作用中使用者清單中選取了部分使用者 (因為其名稱旁的圓圈是填滿的)。](media/EDU-Lic-Active-Users-List.png)
3. 在頂端選取 **[管理產品授權]**。

   ![[管理產品授權] 索引標籤的螢幕擷取畫面，下面有一位使用者列為 [未授權]。](media/EDU-Lic-Manage-Product-Licenses.png)
4. 在 **[管理產品授權]** 窗格中，選取 **[新增到現有產品授權指派]** > **[下一步]**。

   ![[管理產品授權] 視窗的螢幕擷取畫面，其中已選取 [新增到現有產品授權指派] 選項按鈕。](media/EDU-Lic-Add-Existing-Product.png)
5. 在 **[新增到現有產品]** 窗格中，針對您已選取要指派授權的使用者，將開關切換到 **[開啟]** 位置。 請確認已選取 **[Microsoft Teams]** 和 **[Office 網頁版 (教育)]**。

   ![在 [新增到現有產品] 索引標籤上已選取 [Microsoft Teams] 和 [Office 網頁版 (教育)] 的螢幕擷取畫面。](media/EDU-Lic-Add-Existing-Products.png)

   根據預設，與這些授權相關的所有服務都會自動指派給使用者。 您可以限制使用者能使用的服務。 針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。
6. 在窗格底部，選取 [新增] > [關閉]。