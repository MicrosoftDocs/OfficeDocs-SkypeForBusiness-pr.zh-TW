---
title: PSTN 使用報告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
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
description: 新的商務用 Skype 系統管理中心報告區域會顯示您組織中的通話和音訊會議活動。 它可讓您深入探索報表，讓您更精確地瞭解每個使用者的活動。 例如，您可以使用 [商務用 Skype PSTN 使用詳細資料] 報告來查看輸入/撥出通話中花費的分鐘數，以及這些通話的成本。 您可以查看音訊會議 PSTN 使用狀況詳細資料（包括通話成本），以便了解您的使用方式，以及撥打帳單詳細資料來判斷貴組織內的使用方式。
ms.openlocfilehash: a489277eceaab533fc03ac7017dcc217b4071bc6
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "42582880"
---
# <a name="pstn-usage-report"></a>PSTN 使用報告

新的商務用 Skype 系統管理中心**報告**區域會顯示您組織中的通話和音訊會議活動。 它可讓您深入探索報表，讓您更精確地瞭解每個使用者的活動。 例如，您可以使用 [**商務用 SKYPE PSTN 使用詳細資料**] 報告來查看輸入/撥出通話中花費的分鐘數，以及這些通話的成本。 您可以查看音訊會議 PSTN 使用狀況詳細資料（包括通話成本），以便了解您的使用方式，以及撥打帳單詳細資料來判斷貴組織內的使用方式。
  
查看[報表總覽](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)以取得更多可用報表。
  
此報告以及其他商務用 Skype 報告，提供活動的詳細資料，包括在整個組織中呼叫使用方式。 當您調查、規劃及針對貴組織進行其他業務決策，以及設定[通訊信用額度](/microsoftteams/what-are-communications-credits)時，這些詳細資料非常有用。
  
> [!NOTE]
> 當您以系統管理員身分登入 Microsoft 365 系統管理中心時，您可以看到所有商務用 Skype 報告。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>如何取得商務用 Skype PSTN 使用狀況詳細資料包告

![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示

- 移至系統管理中心 > 系統**管理中心** > **商務用 Skype 系統管理中心** > **報告** > **PSTN 使用狀況詳細資料**。
    
    > [!NOTE]
    > 視您擁有的 Office 365 訂閱而定，您可能不會看到這裡顯示的所有產品和報表。 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>解讀商務用 Skype PSTN 使用量報告

您可以透過查看每個顯示的欄，來取得使用者的商務用 Skype PSTN 使用量。
  
這就是報表看起來的樣子。
  
![商務用 Skype PSTN 使用方式報告](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![數位1](../images/sfbcallout1.png)<br/>下表顯示每個使用者的所有 PSTN 使用量明細。 這會顯示已指派商務用 Skype 的所有使用者以及其 PSTN 使用方式。 您可以在資料表中新增/移除資料行。
*    [**通話 id** ] 是通話的通話 id。 它是呼叫 Microsoft 服務支援時所使用之通話的唯一識別碼。
*    [**使用者識別碼**] 是使用者的登入名稱。
*    [**電話號碼**] 是已接收撥入通話通話或撥出通話電話號碼的商務用 Skype 電話號碼。
*    [**使用者位置**] 是使用者所在的國家/地區。
*    **本機號碼**為撥入通話的電話號碼（來電者識別碼），或撥打電話的電話號碼，或通話發出的 Skype 電話號碼。
*    **呼叫類型**：此通話是 PSTN 撥出或撥入通話，以及撥打電話類型（例如使用者或音訊會議發出的通話）。 您可能會看到的呼叫類型如下： 

     **通話方案呼叫類型** 
     *    **user_in** （使用者收到輸入 PSTN 通話） 
     *    **user_out** （使用者已發出出站 PSTN 通話） 
     *    **user_out_conf** （使用者已將2個或更多 PSTN 參與者加入通話中，例如3路會議通話） 
     *    **user_out_transfer** （使用者已將來電轉接至 PSTN 號碼） 
     *    **user_out_forwarding** （使用者將呼叫轉寄至 PSTN 號碼）

     **音訊會議呼叫類型**
     *    **conf_in** （撥入通話至音訊會議橋）。 針對此通話類型的記錄，[**使用者識別碼**] 欄中指定的使用者會對應到會議的召集人。
     *    **conf_out** （來自音訊會議橋接器的撥出通話，通常是用來在會議中新增 PSTN 號碼）。 針對此通話類型的記錄，[**使用者識別碼**] 欄中指定的使用者會對應到會議的召集人。

     **整合通訊應用程式（UCAP）** 
     *    **ucap_in** （針對自動語音應答或通話佇列等 UC 應用程式的入站 PSTN 呼叫） 
     *    **ucap_out** （來自 UC 應用程式的輸出 PSTN 呼叫，例如自動語音應答或通話佇列）
     *    **注意：** 從 UC 應用程式傳送給使用者的呼叫（例如自動語音應答或呼叫佇列）不會出現在 PSTN 使用狀況報告中，因為這些呼叫腿是對等（P2P）音訊通話。 您可以在商務用 Skype 系統 > 管理中心的 [商務用 Skype 通話分析] 底下存取 P2P 通話，然後依使用者名稱或 SIP 位址來搜尋，依日期/時間和/或來源 CLID （通話行識別碼）來進行通話。 
*     
     **國內/國際**是根據使用者的位置，告訴您所設定的通話是國內（在國家/地區內）還是國際（位於國家/地區外）。 
*    [**目的地撥號**] 是您撥打的國家/地區目的地（例如華北、德國或美國）的名稱。 
*    **Number type**是來自使用者電話號碼、服務或免付費電話號碼的電話號碼類型。  
*    **開始時間（UTC）** 是呼叫開始或撥入的時間。 
*    [**持續時間**] 是通話的連線時間。  
*    **ConfID**是音訊會議的會議 ID。 
*    [**收取費用**] 是支付給您帳戶之通話的金額或成本。 
*    **貨幣**是用來計算通話成本的貨幣類型。 
*    **功能**是通話使用的授權。 您可能會看到的授權類型如下： 
     *    **MCOPSTNPP** -通訊點數 <br/> **MCOPSTN1** -國內通話方案（3000美元/1200 分歐盟方案） 
     *    **MCOPSTN2** -國際通話方案 
     *    **MCOPSTN5** -國內通話方案（120最小通話方案） 
     *    **MCOPSTN6** -國內通話方案（240 min 通話方案）注意：有限的可用性
     *    **MCOMEETADD** -音訊會議
     *    **MCOMEETACPEA** -每分鐘付款音訊會議
     
> [!NOTE]
> 如果您想要執行報表，以便只包含通話或會議訂閱中不包含的每分鐘工資通話，請使用「MCOPSTNPP」功能篩選報表。 如此一來，就會提供每分鐘工資通話的明細。  針對每分鐘付費音訊會議，請依「MCOMEETACPEA」篩選，而不是「MCOPSTNPP」。  

> [!NOTE]
> 在某些欄位中，您可能也會看到「沒有資料」。 "無資料" 表示該欄位不適用於呼叫類型或功能。 

> [!NOTE]
> 如果您有 Telstra 通話方案，就不會在 PSTN 使用狀況報告中看到任何通話詳細資料記錄。 如需報告需求，請與 Telstra。 
***
![數位2](../images/sfbcallout2.png)<br/>按一下以將欄拖曳至依據特定欄進行分組，如果您想要建立一個將一或多個欄中的所有資料組成群組的視圖 **，請在這裡拖曳欄標題**。
 ***
![數位3](../images/sfbcallout3.png)<br/>您也可以透過按一下或敲擊 [**匯出至 Excel** ] 按鈕，將報告資料匯出為逗號分隔的 Excel 檔案。 除非國家或地區的特定規定禁止將資料保留12個月，否則您可以從目前日期開始匯出一年的資料。<br/><br/> 這會匯出所有使用者的資料，並可讓您進行簡單的排序與篩選，以進行進一步分析。 如果您的使用者少於2000，您可以在報表本身的資料表中排序和篩選。 
    
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他商務用 Skype 報表嗎？

- [商務用 Skype 活動報告](activity-report.md)您可以查看使用者使用對等、組織的方式，以及參與會議會話的數量。
    
- [商務用 Skype 裝置使用方式報告](device-usage-report.md)您可以查看裝置，包括已安裝商務用 Skype 應用程式的 Windows 作業系統和行動裝置，以及用於 IM 和會議的行動裝置。
    
- [商務用 Skype 會議召集人活動報告](conference-organizer-activity-report.md)您可以查看您的使用者使用 IM、音訊/視頻、應用程式共用、Web、/dial out-協力廠商及/dial 的方式來組織會議的數量。
    
- [商務用 Skype 會議參與者活動報告](conference-participant-activity-report.md)您可以查看有多少 IM、音訊/視頻、應用程式共用、網頁和撥出音訊會議都在參與。
    
- [商務用 Skype 對等活動報告](peer-to-peer-activity-report.md)您可以查看您的使用者使用 IM、音訊/視頻、應用程式共用和傳送檔案的數量。
    
- [商務用 Skype 使用者封鎖報告](users-blocked-report.md)您可以看到貴組織中已封鎖進行 PSTN 通話的使用者。

- [商務用 SKYPE PSTN 分鐘池報告](pstn-minute-pools-report.md)您可以查看貴組織內的當月所消耗的分鐘數。

- [商務用 Skype 會話詳細資料包表](session-details-report.md)您可以查看個別使用者的通話體驗的詳細資料。
    
## <a name="related-topics"></a>相關主題
[系統管理中心的活動報告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
