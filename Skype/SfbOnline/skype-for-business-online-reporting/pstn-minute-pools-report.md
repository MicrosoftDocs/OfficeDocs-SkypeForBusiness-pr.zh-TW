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
description: 新的商務用 Skype 系統管理中心報告區域會顯示您組織中的通話和音訊會議活動。 它可讓您深入探索報表，讓您更精確地瞭解每個使用者的活動。 例如，您可以使用商務用 Skype PSTN 分鐘池報告來查看在您組織中的當月期間消耗的分鐘數。
ms.openlocfilehash: 2777b4f32b99a086110b75ca527eda29b0842b6e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692428"
---
# <a name="pstn-minute-pools-report"></a>PSTN 分鐘集區報告

>[!NOTE]
>此報告僅供預覽客戶使用。

新的商務用 Skype 系統管理中心**報告**區域會顯示您組織中的通話和音訊會議活動。 它可讓您深入探索報表，讓您更精確地瞭解每個使用者的活動。 例如，您可以使用商務用**SKYPE PSTN 分鐘池**報告來查看在您組織中的當月期間消耗的分鐘數。
  
查看[報表總覽](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)以取得更多可用報表。
  
此報告以及其他商務用 Skype 報告，提供您組織中活動的詳細資料。 這些詳細資料在調查、規劃及針對組織進行其他業務決策時非常有用，以及設定[通訊點數](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> 當您以系統管理員身分登入 Microsoft 365 系統管理中心時，您可以看到所有商務用 Skype 報告。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>如何取得商務用 Skype PSTN 分鐘池報告

![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示

- 移至系統管理中心 > 系統**管理中心** > **商務用 Skype 系統管理中心** > **報告** > **PSTN 分鐘池**。
    
> [!NOTE]
> 視您擁有的 Office 365 訂閱而定，您可能不會在這裡看到所有相同的詳細資料。 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>解讀商務用 Skype PSTN 分鐘池報告

您可以查看每個顯示的欄，以取得使用者的商務用 Skype 分鐘池。
  
這就是報表看起來的樣子。
  
## 

![商務用 Skype PSTN 分鐘池報告](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![數位1](../images/sfbcallout1.png)<br/>下表顯示的是依據授權（功能）和使用位置來細分分鐘數。 
*    **功能**是用於通話的授權/服務方案。 您可能會在此報告中看到的授權/服務方案包括：
     * MCOPSTN1-國內通話方案（3000-每分鐘美國/1200-1 分鐘歐盟方案
     * MCOPSTN2-國內 & 國際通話方案，您可以在此查看國內的泳池（3000-minute/加拿大/PR，1200-minute 歐洲國家/地區）和國際泳池（600-分鐘）。 只要在行事曆月份內達到國內或國際 cap，就會達到分鐘帽。 
     * MCOPSTN5-國內通話方案（120分鐘通話方案）
     * MCOPSTN6-國內通話方案（240分鐘通話方案）
     * MCOMEETADD-音訊會議
*    [**功能描述**] 是通話使用之授權類型的描述。
*    [**國家/分鐘] 池**是共用分鐘池之使用者的授權使用位置。 
*    [已**使用的分鐘**數] 是每個月所使用的分鐘數。
*    [**總分鐘**數] 是指月份中可用的總分鐘數。 
*    [已**使用百分比**] 是該月份所用的分鐘數百分比。 
***
![數位2](../images/sfbcallout2.png)<br/>按一下以將欄拖曳至依據特定欄進行分組，如果您想要建立一個將一或多個欄中的所有資料組成群組的視圖 **，請在這裡拖曳欄標題**。 
***
![數位3](../images/sfbcallout3.png)<br/>您也可以按一下或敲擊 [**匯出至 excel** ] 按鈕，將報告資料匯出至 Excel .csv 檔案。 <br/><br/> 這會匯出所有使用者的資料，並可讓您進行簡單的排序與篩選，以進行進一步分析。 如果您的使用者少於2000個，您可以在報表本身的資料表中排序和篩選。 如果您有超過2000的使用者，若要篩選和排序，您必須匯出資料。
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他商務用 Skype 報表嗎？

- [商務用 Skype 活動報告](activity-report.md)您可以查看使用者使用對等、組織的方式，以及參與會議會話的數量。
    
- [商務用 Skype 裝置使用方式報告](device-usage-report.md)您可以查看裝置，包括已安裝商務用 Skype 應用程式的 Windows 作業系統和行動裝置，以及用於 IM 和會議的行動裝置。
    
- [商務用 Skype 會議召集人活動報告](conference-organizer-activity-report.md)您可以查看您的使用者使用 IM、音訊/視頻、應用程式共用、Web、/dial out-協力廠商及/dial 的方式來組織會議的數量。
    
- [商務用 Skype 會議參與者活動報告](conference-participant-activity-report.md)您可以查看有多少 IM、音訊/視頻、應用程式共用、網頁和撥出音訊會議都在參與。
    
- [商務用 Skype 對等活動報告](peer-to-peer-activity-report.md)您可以查看您的使用者使用 IM、音訊/視頻、應用程式共用和傳送檔案的數量。
    
- [商務用 Skype 使用者封鎖報告](users-blocked-report.md)您可以看到貴組織中已封鎖進行 PSTN 通話的使用者。

- [商務用 Skype 會話詳細資料包表](session-details-report.md)您可以查看個別使用者的通話體驗的詳細資料。
    
## <a name="related-topics"></a>相關主題
[系統管理中心的活動報告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
