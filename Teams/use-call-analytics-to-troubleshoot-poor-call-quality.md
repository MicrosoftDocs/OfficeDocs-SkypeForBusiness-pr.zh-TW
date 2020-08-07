---
title: 使用呼叫分析來排查不佳的通話品質問題
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用針對裝置、網路和連線的每個使用者呼叫分析詳細資料，以解決 Microsoft 團隊通話和會議的使用者問題。
ms.openlocfilehash: 8bee41e79f2610adcb9a1fed3f895c728526f5ea
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583622"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>使用呼叫分析來排查不佳的通話品質問題

本文說明如何使用呼叫分析來針對個別使用者進行較差的 Microsoft 團隊通話或會議品質（如果您是團隊管理員或團隊溝通支援專家或工程師）。


  
## <a name="call-analytics-permissions"></a>呼叫分析許可權

本文假設您已設定通話分析。 如果您還沒有，請閱讀[設定小組的呼叫分析](set-up-call-analytics.md)。

## <a name="introduction-to-call-analytics"></a>通話分析簡介

[通話分析] 會顯示針對您 Office 365 帳戶中每位使用者的小組通話與會議的詳細資訊。 它包含裝置、網路、連線和通話品質的相關資訊 (其中任何一項都可能是) 通話或會議品質不佳的因素。 如果您上傳的是建築物、網站和租使用者資訊，也會針對每個通話和會議顯示此資訊。 使用呼叫分析，協助您找出使用者為何通話或會議體驗不佳的原因。

[通話分析] 會顯示通話或會議的每個腿，例如，從一個參與者到第二個參與者。 透過分析這些詳細資料，團隊管理員可以隔離問題區域並找出品質欠佳的根本原因。
   
就像團隊管理員一樣，您可以完全存取每位使用者的所有呼叫分析資料。 此外，您也可以將 Azure Active Directory 角色指派給支援人員。 若要深入瞭解這些角色，請參閱[提供支援和技術人員的許可權](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。 不要錯過[每個團隊是否支援 role？](#what-does-each-teams-support-role-do)在下方。

## <a name="where-to-find-per-user-call-analytics"></a>尋找每個使用者的呼叫分析的位置

若要查看使用者的所有呼叫資訊和資料，請移至[團隊系統管理中心](https://admin.teams.microsoft.com)。 在 [**使用者**] 底下，選取使用者，然後在使用者的設定檔頁面面上開啟 [**通話記錄**] 索引標籤。 您可以在這裡找到該使用者在過去30天內的所有通話與會議。

![所有分析使用者資料的螢幕擷取畫面](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

若要取得指定會話的其他資訊，包括詳細的媒體和網路統計資料，請按一下某個會話以查看詳細資料。

![呼叫分析使用者會話資料的螢幕擷取畫面](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>每個團隊支援角色的功能是什麼？

**團隊通訊支援專家** (第1層支援) 處理基本的通話品質問題。 他們不會調查會議的問題。 相反地，他們會收集相關資訊，然後升級至通訊支援工程師。 

**團隊通訊支援工程師** (第2層支援) 可在小組通訊支援專家隱藏的詳細通話記錄中查看資訊。 下表列出每個小組通訊支援角色所提供的資訊。

下表說明每個使用者資訊可供每個通訊支援角色使用。

|**活動**|**錯誤資訊**|溝通支援**專家**所能看到的內容|溝通支援**工程師**所能看到的內容|
|:-----|:-----|:-----|:-----|
|**撥** <br/> |來電者名稱  <br/> |僅限代理程式搜尋的使用者名稱。  <br/> |[使用者名稱]。  <br/> |
||收件者名稱  <br/> |顯示為內部使用者或外部使用者。  <br/> |收件者名稱。  <br/> |
||來電者電話號碼  <br/> |除後三位數以外的整個電話號碼都會以星號符號加以混淆。 例如，15552823 * * *。  <br/> |除後三位數以外的整個電話號碼都會以星號符號加以混淆。 例如，15552823 * * *。  <br/> |
||收件者電話號碼  <br/> |除後三位數以外的整個電話號碼都會以星號符號加以混淆。 例如，15552823 * * *。  <br/> |除後三位數以外的整個電話號碼都會以星號符號加以混淆。 例如，15552823 * * *。  <br/> |
||**通話詳細資料**  > [**高級**] 索引標籤 <br/> |未顯示資訊。  <br/> |顯示所有的詳細資料，例如裝置名稱、IP 位址、子網對應等。  <br/> |
||**通話詳細資料**  > [**高級**  >  ][**調試**] 索引標籤 <br/> |未顯示資訊。  <br/> |顯示所有的詳細資料，例如 DNS 尾碼和 SSID。  <br/> |
|**會議** <br/> |參與者名稱  <br/> |僅限代理程式搜尋的使用者名稱。 已識別為內部使用者或外部使用者的其他參與者。  <br/> |顯示所有名稱。  <br/> |
||參與者計數  <br/> |參與者數目。  <br/> |參與者數目。  <br/> |
||會話詳細資料  <br/> |顯示的會話詳細資料（含例外狀況）。 只顯示代理程式搜尋的使用者名稱。 已識別為內部使用者或外部使用者的其他參與者。 以星號符號加以混淆之電話號碼的後三位數。  <br/> |顯示 [會話詳細資料]。 顯示 [使用者名稱] 和 [會話詳細資料]。 以星號符號加以混淆之電話號碼的後三位數。  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a>疑難排解使用者通話品質問題 

1. 開啟 [團隊管理中心] (https://admin.teams.microsoft.com) 並使用您的小組通訊支援或團隊管理員認證登入。

2. 在**儀表板**上的 [**使用者搜尋**] 中，開始輸入您想要排查其通話問題之使用者的名稱或 SIP 位址，或選取 [**查看使用者**] 來查看使用者清單。

3. 從清單中選取使用者。

4. 選取 [**通話記錄**]，然後選取您想要疑難排解的通話或會議。
    
5. 選取 [**高級**] 索引標籤，然後尋找黃色和紅色專案，指出通話品質或連線問題不佳。
    
    在每個通話或會議的 [會話詳細資料] 中，次要問題會以黃色顯示。 如果有黃色，則它不在正常範圍之內，可能會造成問題，但不太可能是問題的主要原因。 如果有紅色，這是一個很重要的問題，這可能是這個會話的通話品質不佳的主要原因。 
      
在少數情況下，音訊會話的體驗資料品質不會收到。 這通常是由中斷的通話或與用戶端的連線所導致。 發生這種情況時，**無法使用**[會議評等]。
  
對於 (QoE) 資料的音訊會話，您可以使用下清單格來說明將會話限定為**不良**的主要問題。
  
|**問題**|**圖**|**描述**|
|:-----|:-----|:-----|
|撥號設定  <br/> |工作階段  <br/> |錯誤碼 Ms-診斷程式20-29 指出通話設定失敗。 使用者無法加入通話或會議。  <br/> |
|音訊網路分類不佳通話  <br/> |工作階段  <br/> |網路品質問題 (例如，遇到資料包遺失、抖動、NMOS 下降、RTT 或隱藏比率) 。  <br/> |
|裝置無法運作  <br/> |裝置  <br/> | 裝置無法正常運作。 裝置的運作比例如下： <br/>  DeviceRenderNotFunctioningEventRatio >= 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0.005 <br/> |
   

## <a name="related-topics"></a>相關主題

[設定每個使用者的呼叫分析](set-up-call-analytics.md)



  
 
