---
title: 設定通話分析
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 設定並使用呼叫分析來識別和疑難排解商務用 Skype 和 Microsoft 團隊通話品質問題。
ms.openlocfilehash: fe46ee580554969d26395b26117649ab8ada2ea0
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838053"
---
# <a name="set-up-call-analytics"></a>設定通話分析

在團隊或商務用 Skype Online 系統管理員中，您可以使用呼叫分析來疑難排解商務用 Skype 和 Microsoft 團隊通話品質與連線問題。 您可能會發現在 [呼叫分析] 中設定下列功能很有用：
  
- 設定許可權讓其他人員（例如支援者的工程師）使用呼叫分析，但不能存取 Microsoft 團隊系統管理中心的其餘部分。 
    
- 透過上傳 tsv 或 .csv 資料檔案，將建築物、網站和租使用者資訊新增至呼叫分析。
    
**[通話分析] 現已提供給 Microsoft [團隊管理中心**]。 若要查看使用者的所有通話資訊和資料，請使用 [**通話記錄**] 索引標籤。您可以透過執行下列其中一項動作來查看使用者的設定檔頁面面：

- 從儀表板搜尋使用者。
  
   ![儀表板上使用者搜尋的螢幕擷取畫面](media/set-up-call-analytics-image-1.png)

-  選取左側導覽中的 [**使用者**]。

   ![左側導覽的螢幕擷取畫面](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>設定呼叫分析許可權
<a name="BKMK_SetCAPerms"></a>

就像管理員一樣，您擁有呼叫分析的所有功能的完整存取權。 此外，您也可以將 Azure Active Directory 角色指派給支援人員。 將團隊通訊支援專家角色指派給應該擁有有限的通話分析視圖的使用者。 指派團隊通訊支援工程師角色給需要存取呼叫分析完整功能的使用者。 兩個許可權等級都無法存取 Microsoft 團隊系統管理中心的其他部分。

> [!NOTE]
> 通訊支援專家角色相當於第1層支援，且溝通支援工程師角色相當於第2層支援。

如需有關團隊管理員角色的詳細資訊，請參閱[使用 Microsoft 團隊管理員角色管理團隊](using-admin-roles.md)。 
  
通訊支援專家處理基本的通話品質問題。 他們不會調查會議的問題。 相反地，他們會收集相關資訊，然後升級至通訊支援工程師。 通訊支援工程師請參閱與通訊支援專家隱藏的詳細通話記錄中的資訊。 下表提供通訊支援專家與通訊支援工程師在使用呼叫分析時所提供資訊的概覽。

|**操作**|**通話分析中的資訊**|**溝通支援專家所能看到的內容**|**溝通支援工程師所能看到的內容**|
|:-----|:-----|:-----|:-----|
|**撥** <br/> |來電者名稱  <br/> |僅限代理程式搜尋的使用者名稱。  <br/> |[使用者名稱]。  <br/> |
||收件者名稱  <br/> |顯示為內部使用者或外部使用者。  <br/> |收件者名稱。  <br/> |
||來電者電話號碼  <br/> |除後三位數以外的整個電話號碼都會以星號符號加以混淆。 例如，15552823 * * *。  <br/> |除後三位數以外的整個電話號碼都會以星號符號加以混淆。 例如，15552823 * * *。  <br/> |
||收件者電話號碼  <br/> |除後三位數以外的整個電話號碼都會以星號符號加以混淆。 例如，15552823 * * *。  <br/> |除後三位數以外的整個電話號碼都會以星號符號加以混淆。 例如，15552823 * * *。  <br/> |
||**[通話詳細資料** > **] 索引**標籤 <br/> |未顯示資訊。  <br/> |顯示所有的詳細資料，例如裝置名稱、IP 位址、子網對應等。  <br/> |
||**通話詳細資料** > [**高級** > **調試**] 索引標籤 <br/> |未顯示資訊。  <br/> |顯示所有的詳細資料，例如 DNS 尾碼和 SSID。  <br/> |
|**會議** <br/> |參與者名稱  <br/> |僅限代理程式搜尋的使用者名稱。 已識別為內部使用者或外部使用者的其他參與者。  <br/> |顯示所有名稱。  <br/> |
||參與者計數  <br/> |參與者數目。  <br/> |參與者數目。  <br/> |
||會話詳細資料  <br/> |顯示的會話詳細資料（含例外狀況）。 只顯示代理程式搜尋的使用者名稱。 已識別為內部使用者或外部使用者的其他參與者。 以星號符號加以混淆之電話號碼的後三位數。  <br/> |顯示 [會話詳細資料]。 顯示 [使用者名稱] 和 [會話詳細資料]。 以星號符號加以混淆之電話號碼的後三位數。  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>指派管理員角色來設定許可權
<a name="BKMK_SetUpTier"> </a>

若要瞭解如何在 Azure Active Directory 中指派系統管理角色，請參閱[在 Azure Active directory 中查看和指派角色](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>上傳. tsv 或 .csv 檔案，以新增建築物、網站和租使用者資訊
<a name="BKMK_UploadFiles"> </a>

您可以透過上傳 .csv 或 tsv 檔案，將建築物、網站和租使用者資訊新增至呼叫分析。 在所有這些資訊的情況下，呼叫分析可以將 IP 位址對應至物理位置。 您或技術支援人員可能會發現此資訊有助於找出通話問題的趨勢。 例如，為什麼同一個建築物中的許多使用者都有類似的通話品質問題？ 

如果您是團隊和商務用 Skype 系統管理員，您可以使用 [團隊] & 商務用 Skype 通話品質儀表板中的現有資料檔案。 首先，您要從 [通話品質儀表板] 下載檔案，然後將它上傳到 [呼叫分析]。 

- 若要下載現有的資料檔，請移至**Microsoft 團隊系統管理中心** > **的通話品質儀表板** > **[立即上傳**]。 在 [**我**的上傳] 清單中，按一下您想要的檔案旁的 [**下載**]。

- 若要上傳新檔案，請移至**Microsoft 團隊系統管理中心** > **位置**，然後選取 **[上傳位置資料**] 或 [**取代位置資料**]。
  
如果您要從頭開始建立 tsv 或 .csv 檔案，請參閱租使用者[資料檔案格式及建立資料檔案結構](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)。
  
## <a name="related-topics"></a>相關主題
<a name="BKMK_UploadFiles"> </a>

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析和通話品質儀表板](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
