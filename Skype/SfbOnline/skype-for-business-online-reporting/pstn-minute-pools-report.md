---
title: PSTN 分鐘集區報告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
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
description: 新的系統管理商務用 Skype報告區域會顯示貴組織的通話和音訊會議活動。 它可讓您深入瞭解報表，以進一步深入瞭解每個使用者的活動。 例如，您可以使用 PSTN 商務用 Skype分鐘數報告，查看貴組織內當月所耗用分鐘數。
ms.openlocfilehash: dae86688a5fb0204802f62d28504c3454613bb3d7f7d23f17d09972b94303390
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57850248"
---
# <a name="pstn-minute-pools-report"></a>PSTN 分鐘集區報告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

>[!NOTE]
>此報表僅適用于預覽客戶。

新的系統商務用 Skype系統管理中心 **報告** 區域會顯示貴組織的通話和音訊會議活動。 它可讓您深入瞭解報表，以進一步深入瞭解每個使用者的活動。 例如，您可以使用 **PSTN** 商務用 Skype分鐘數報告，查看貴組織內當月所耗用分鐘數。
  
請查看報告 [概觀以](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 查看更多可用的報告。
  
此報告與其他報告商務用 Skype一起，提供您整個組織活動的詳細資訊。 這些詳細資料在調查、規劃及為貴組織做出其他商務決策，以及設定通訊信用額度時非常[實用](/microsoftteams/what-are-communications-credits)。
  
> [!NOTE]
> 當您以系統管理員的商務用 Skype登入時，可以看到所有Microsoft 365 系統管理中心。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>如何取得 PSTN 商務用 Skype分鐘數報表

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

- 前往系統管理中心>**系統** 管理商務用 Skype  >    >  **報告**  >  **PSTN 分鐘數庫**。
    
> [!NOTE]
> 視您Microsoft 365訂閱Office 365，您可能不會在這裡看到所有相同的詳細資料。 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>解譯商務用 Skype PSTN 分鐘數庫報告

您可以查看顯示的每一欄，商務用 Skype查看使用者的分鐘數庫。
  
這就是報表的外觀。

![商務用 SkypePSTN 分鐘數庫報告](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![數位 1](../images/sfbcallout1.png)<br/>下表顯示授權和使用位置 (分鐘) 明細。 
*    **功能** 是通話所使用的授權/服務方案。 您可能會在此報告中看到授權/服務方案包括：
     * MCOPSTN1 - 國內通話方案 (3000 分鐘美國/1200 分鐘的歐盟方案
     * MCOPSTN2 - 國內 & (國際通話方案，您可從該計畫看到 3000 分鐘的美國/加拿大/PR、1200 分鐘的歐洲國家/地區) 以及 600 分鐘的 (國際) 。 每當在日曆月份內達到國內 -OR- 國際上限時，即會達到分鐘數上限。 
     * MCOPSTN5 - 國內通話方案 (120 分鐘的通話方案) 
     * MCOPSTN6 - 國內通話方案 (240 分鐘的通話方案) 
     * MCOMEETADD - 音訊會議
*    **功能描述** 是通話所使用之授權類型的描述。
*    **國家/地區分鐘** 數庫是共用分鐘 () 使用者之授權使用位置。 
*    **使用分鐘** 數是每個月使用的分鐘數。
*    **總分鐘** 數是一個月的總可用分鐘數。 
*    **使用百分比** 是當月使用的分鐘數百分比。 
***
![數位 2](../images/sfbcallout2.png)<br/>若要將欄拖曳到按特定欄分組，如果您想要建立將一或多個資料行中所有資料組成群組的視圖，請在這裡拖放欄標題。 
***
![數位 3](../images/sfbcallout3.png)<br/>您也可以按一下或點選匯出至Excel .csv，將報表資料匯出至 **Excel檔案。** <br/><br/> 這會匯出所有使用者的資料，並可讓您執行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 人，您可以在報表本身的表格內排序和篩選。 如果您有超過 2000 個使用者，若要篩選和排序，您必須匯出資料。
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他商務用 Skype報表？

- [商務用 Skype活動報告](activity-report.md)您可以查看使用者使用對等、組織及參與會議會話的多少。
    
- [商務用 Skype裝置使用方式報告](device-usage-report.md)您可以查看裝置，包括Windows型作業系統，以及已安裝應用程式商務用 Skype且用於 IM 和會議的行動裝置。
    
- [商務用 Skype會議召集人活動報告](conference-organizer-activity-report.md)您可以查看使用者組織使用 IM、音訊/視像、應用程式共用、Web、/撥出 - 協力廠商和 /dial out - Microsoft 的會議。
    
- [商務用 Skype會議參與者活動報告](conference-participant-activity-report.md)您可以查看有多少 IM、音訊/視像、應用程式共用、Web 和撥出音訊會議參與。
    
- [商務用 Skype對等活動報表](peer-to-peer-activity-report.md)您可以瞭解使用者正在使用 IM、音訊/視像、應用程式共用和傳輸檔案。
    
- [商務用 Skype封鎖報表的使用者](users-blocked-report.md)您可以看見貴組織中遭到封鎖的使用者，無法撥打 PSTN 通話。

- [商務用 Skype會話詳細資料包表](session-details-report.md)您可以查看個別使用者的通話體驗詳細資料。
    
## <a name="related-topics"></a>相關主題
[系統管理中心的活動報告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
