---
title: 工作階段詳細資報告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: 報告儀表板會顯示您組織中Microsoft 365 Office 365或Office 365活動概觀。 它可讓您深入查看個別的產品層級報告，以進一步深入瞭解每個產品內的活動。
ms.openlocfilehash: 522a82bf9b93a590f8f319d59e805b23ba34d4665b34eb05541aa18d1b9ba89e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308014"
---
# <a name="session-details-report"></a>工作階段詳細資報告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

報表 **儀表板** 會顯示您組織中所有Microsoft 365 Office 365活動概觀。 它可讓您深入查看個別的產品層級報告，以進一步深入瞭解每個產品內的活動。 例如，您可以使用 商務用 Skype **會話詳細資料** 報表來查看個別使用者的通話體驗詳細資料。
  
請查看 [報告概觀](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) ，以查看更多可用的報告。
  
此報告與其他報告商務用 Skype提供您活動的詳細資訊，包括整個組織的會話詳細資料。 當您調查、規劃及為貴組織做出其他商務決策，以及設定通訊信用額度時，這些詳細資料非常 [實用](/microsoftteams/what-are-communications-credits)。
  
> [!NOTE]
> 當您以系統管理員的商務用 Skype登入時，可以看到所有Microsoft 365 系統管理中心。 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>如何取得會話詳細商務用 Skype報表

1. 前往系統管理中心> **報告**
    
2. 從 **左側** 功能表選取 [報表，然後按一下 [ **使用方式**> 。
    
3. 在 [選取報表 **商務用 Skype****清單中，按一下 [會話詳細資料**> 。
    
    > [!TIP]
    > 如果您未列出此報表，請前往系統管理商務用 Skype ****  >  **報告**  >  **會話詳細資料**。 
  
    > [!IMPORTANT]
    > 視您Microsoft 365訂閱Office 365，您可能不會看到此處顯示的所有產品與報表。 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>解譯商務用 Skype會話詳細資料包表

您可以查看每個顯示的欄，商務用 Skype查看使用者的會話詳細資料。
  
這就是報表的外觀。
  
![商務用 Skype會話詳細資料包表儀表板。](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![數位 1](../images/sfbcallout1.png)<br/>**使用別名搜尋** 使用者可讓您搜尋單一使用者，並顯示下表中該使用者的所有會話詳細資料。 
***
![數位 2](../images/sfbcallout2.png)<br/>**輸入開始日期可讓您** 輸入開始日期。 您可以使用日曆來選取日期，或手動輸入日期。 此欄位必須填上。
***
![數位 3](../images/sfbcallout3.png)<br/>**輸入至日期時間** 可讓您輸入結束日期。 您可以使用日曆來選取日期，或手動輸入日期。 如果未設定結束日期，預設值為自開始日期起 30 天。
***
![數位 4](../images/sfbcallout4.png)<br/>下表顯示每個使用者所有會話詳細資料明細。 這會顯示所有已指派商務用 Skype使用者及其會話資訊。 您可以在表格中新增/移除欄。 <br/><br/>每個會話的表格都有下列欄：
*    **對話方塊識別碼** 是 SIP 會話唯一識別碼的識別碼。
*    **媒體類型描述** 描述會話是電話會議或 P2P 會話，以及音訊/視 (/應用程式共用) 。
*    **開始時間** 是會話開始的時間。
*    **結束時間** 是會話結束的時間。
*    從 URI 是啟動會話的使用者或服務的 **URI。** 如果使用者從 PSTN 電話啟動會話，則可能是空白。
*    **To URI** 是使用者或服務的 URI，是會話初始的目標。 在會議的情況下，這是召集人的 URI。 如果會話的目標是 PSTN 電話號碼，則可能是空白。
*    **從用戶端版本** 會告訴您啟動會話的使用者或服務所使用的使用者代理程式及用戶端版本。
*    **至用戶端版本** 會告訴您使用者代理程式，以及會話初始目標之使用者或服務所使用的用戶端版本。
*    **會議 URL** 是會議的 SIP URL，如果會話是電話會議。 同一個電話會議中的所有使用者都會有相同的會議 URL。 
*    **從 Tel 號碼** 是會話目標的電話號碼 ，如果適用的話。 電話號碼的最後一位數可能會取代為 'x'，以保護使用者隱私權。
*    **到 Tel number** 是會話目標的電話號碼 ，如果適用的話。 電話號碼的最後一位數可能會取代為 'x'，以保護使用者隱私權。
*    **From 端點識別碼** 是 From 使用者所使用端點的唯一 GUID。 用來識別使用者是否要從同一個端點傳達多個會話。 如果使用者使用 PSTN 電話或會話從服務啟動，則可能是空白。
*    **To 端點識別碼** 是 To 使用者所使用端點的唯一 GUID。 用來識別使用者是否要從同一個端點傳達多個會話。 如果使用者使用 PSTN 電話、會話從服務啟動，或會話無法建立，則可能是空白。
*    **Conf Instance** 是使用會議 URL 的會議實例的唯一 GUID。 週期性會議會具有相同的會議 URL，但會議的每個實例都會有 Conf Instance 的差異。
*    代表 URI 是代表會話建立之委派者之 **URI。** <br/> **由 URI 所推薦** 是提及會話建立之使用者的 URI。
*    **回應代碼** 是建立會話的 SIP 回應程式碼，指出會話是否成功建立。

每個會話都有一個子資料工作表，根據案例提供不同的資料。 下列列出子資料工作表中的可用索引點，供使用者或服務使用。
*    會話選項卡會顯示有關電腦和作業系統的資料。
*    MEDIALINES Tab 會顯示網路連接資訊和裝置資訊。
*    AUDIOSTREAMS Tab 會顯示會話所涉及音訊流的網路績效資料。
*    AUDIOCLIENTEVENTS Tab 會顯示用戶端偵測到影響音訊體驗之問題的資料。
*    AUDIOSIGNALS Tab 會顯示會話的音訊訊號處理資料。
*    APPSHARINGSTREAMS Tab 會顯示會話所涉及之應用程式共用或桌面共用流的網路績效資料。
*    VIDEOCLIENTEVENTS Tab 會顯示用戶端偵測到影響視訊體驗之問題的資料。
*    VIDEOSTREAMS Tab 會顯示會話所涉及視音訊流的網路績效資料。
*    TRACEROUTES Tab 會顯示會話期間透過 traceroute 收集的網路躍點。 會話使用的實際媒體路徑可能會有所不同，而且只有在會話中有音訊時，才能使用這些資料。
*    FEEDBACKREPORTS Tab 會顯示會話中使用者提供的任何通話問卷結束資料。
***
![數位 5](../images/sfbcallout5.png)<br/>若要將欄拖曳到按特定欄分組，如果您想要建立將一或多個資料行中所有資料組成群組的視圖，請在這裡拖放欄標題。 
***
![數位 6](../images/sfbcallout6.png)<br/>您也可以按一下或點選匯出至Excel .csv，將報表資料匯出至 **Excel檔案。** <br/><br/> 這會匯出所有使用者的資料，並可讓您執行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 人，您可以在報表本身的表格內排序和篩選。 如果您有超過 2000 個使用者，若要篩選和排序，您必須匯出資料。  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他商務用 Skype報表？

- [商務用 Skype活動報告](activity-report.md)您可以瞭解使用者使用對等、組織及參與會議會話的多少。
    
- [商務用 Skype裝置使用方式報告](device-usage-report.md)您可以查看裝置，包括Windows型作業系統，以及已安裝應用程式商務用 Skype且用於 IM 和會議的行動裝置。
    
- [商務用 Skype會議召集人活動報告](conference-organizer-activity-report.md)您可以查看使用者組織使用 IM、音訊/視像、應用程式共用、Web、撥入/撥出 - 協力廠商和撥入/撥出 - Microsoft 的會議。
    
- [商務用 Skype會議參與者活動報告](conference-participant-activity-report.md)您可以查看有多少 IM、音訊/視音訊、應用程式共用、Web 和撥入/撥出會議會議參與。
    
- [商務用 Skype對等活動報表](peer-to-peer-activity-report.md)您可以瞭解使用者正在使用 IM、音訊/視像、應用程式共用和傳輸檔案。
    
- [商務用 Skype PSTN 使用方式報告](pstn-usage-report.md)您可以看見用於內/外通話的分鐘數，以及這些通話的成本。

- [商務用 Skype使用者封鎖報表](users-blocked-report.md)您可以看見貴組織中已禁止進行 PSTN 通話的使用者。

- [商務用 Skype PSTN 分鐘](pstn-minute-pools-report.md)數庫報表，您可以查看組織內當月使用的分鐘數。
    
## <a name="related-topics"></a>相關主題
[系統管理中心的活動報告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
