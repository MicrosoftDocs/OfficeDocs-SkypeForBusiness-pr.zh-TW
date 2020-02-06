---
title: 透過商務用 Skype Server 中的工作規劃通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 在商務用 skype Server 中進行通話規劃，在商務用 skype 和您的 PBX 電話系統之間整合，讓使用者可以使用商務用 Skype 來控制其 PBX 電話。
ms.openlocfilehash: 38c61145dcad609c75e7b2e3433efee307f8dc28
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803153"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>透過商務用 Skype Server 中的工作規劃通話
 
在商務用 skype Server 中進行通話規劃，在商務用 skype 和您的 PBX 電話系統之間整合，讓使用者可以使用商務用 Skype 來控制其 PBX 電話。
  
 [透過公司**通話**] 是商務用 skype Server 中的新功能，可讓您將商務用 skype 解決方案與現有的 PBX 電話系統整合。 您可以按一下 [在商務用 Skype 中通話]，在您的部署或外部使用者中呼叫另一個使用者。 通話是使用使用者的 PBX 手機完成。 這可讓使用 PBX 手機的使用者在其豐富的商務用 Skype 交談中包含音訊。 在舊版 Lync Server 遠端通話控制中，這項功能可讓使用者使用 Lync Server 控制其 PBX 手機。 在商務用 Skype Server 中，此功能已由 [透過工作通話] 取代。
  
透過 [通話] 可讓 PBX 電話使用者使用下列功能
  
- [隨打即用] 體驗，透過 PBX 手機提供音訊。
    
- [目前狀態]、[使用者搜尋] 和 [IM 整合]-例如，透過 IM 會話中的工作使用者進行兩次通話，即可透過 PBX 手機提供音訊，將音訊新增至他們的會話中。
    
- 透過 [通話]，將 IM、應用程式共用和檔案傳輸新增至通話的功能。
    
- 一次按一下會議加入功能
    
## <a name="how-it-works"></a>運作方式

透過公司通話使用整合通訊網頁 API （UCWA）作為 PBX 系統與您的商務用 Skype Server 部署之間的後端到後的使用者代理程式（B2BUA），因此不需要電腦支援的電信應用程式（CSTA）閘道進行連接使用 PBX 系統的商務用 Skype 伺服器。 UCWA 是舊版 Lync Server 中引入的服務，可與行動裝置和網路用戶端連線，而且會自動安裝在每個前端伺服器上。
  
### <a name="call-workflow-for-a-call-via-work-call"></a>通話工作流程，透過通話撥打通話

以下說明如何透過工作使用商務用 Skype 伺服器撥打電話給您的使用者：
  
![顯示通話期間透過通話的步驟;首先，來電者會按一下撥號給商務用 Skype 用戶端中的某人;然後 UCWA 會響鈴來電者的電話。 當來電者挑選手機時，會呼叫收件者](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. 使用者在其商務用 Skype 用戶端中選取使用者，然後按一下 [電話] 圖示進行通話。 或者，在 IM 交談期間，使用者按一下即可呼叫與其有會話的使用者。
    
2. 發出通話的使用者的 PBX 電話會開始響鈴。 此電話的呼叫者識別碼會顯示您已設定的全域電話號碼，該電話號碼會顯示在所有使用者撥打電話的本機號碼中。 這個全域電話號碼不是相對於任何一個人的電話的實際電話號碼。 相反地，它是一個視覺信號，讓使用者知道這是自己的撥出電話，而不是同時進行撥入通話。 當您透過工作部署通話時，您應該教育這些使用者關於此全域電話號碼及其意義。
    
3. 發出通話的使用者會挑選其 PBX 電話。 商務用 Skype 接著會啟動呼叫者的語音通話。 
    
4. 當來電者應答時，語音通話就會開始。 如果兩個使用者已經有 IM 會話，就可以繼續。
    
### <a name="joining-a-conference-with-call-via-work"></a>透過 [通話] 加入會議

透過工作使用者進行通話，您可以按一下會議 URL 來加入排程會議。 [商務用 Skype] 接著會顯示 [**撥出至**] 訊息，直到會議服務撥打使用者的 PBX 電話。 [透過工作的通話] 使用者接著會挑選 PBX 電話並加入會議。
  
透過公司使用者的通話也可以使用商務用 Skype 中的 [**立即開會**] 選項來建立 [立即開會] 會議。 然後，使用者會看到 [**撥出至**] 訊息，以及 PBX 電話響鈴。
  
透過工作使用者進行通話，您也可以從商務用 Skype 呼叫會議橋接電話來撥入會議。 如果需要會議 PIN，使用者必須使用 PBX 手機來輸入 PIN。
  
### <a name="incoming-calls"></a>來電

當使用者透過工作接聽商務用 Skype 通話時，PBX 手機和使用者的商務用 Skype 用戶端都會同時撥打（如果使用者已設定同時撥打）。 使用者可以透過挑選 PBX 手機或按一下商務用 Skype 通知中的 [**接受**] 來接受通話。 如果使用者使用商務用 Skype 接受通話，通話的商務用 Skype 視窗就會保持開啟。 但是，如果使用者透過挑選 PBX 手機即可接受通話，則商務用 Skype 通知視窗就會關閉，而且沒有商務用 Skype 會話，只需透過 PBX 電話進行語音通話。
  
當使用者透過工作接聽 PBX 通話時，只需 PBX 電話響鈴。
  
## <a name="limitations-of-call-via-work"></a>透過公司通話的限制

[透過公司通話] 是一種需要進行硬體設定的語音方案，但與完整企業語音或遠端通話控制所提供的功能有所限制。 透過公司通話的限制如下：
  
- 如果透過工作使用者撥打電話已將來電轉接到 [透過工作撥打電話] 撥打電話給來電，而有人嘗試邀請使用者的電話號碼來加入會議，邀請將無法送達使用者。 您應該透過按一下名稱（而非電話號碼）來教育您的使用者邀請參與者加入會議。 
    
- 在通話期間，透過工作通話無法使用增強型911功能和惡意通話追蹤功能。
    
- 啟用 [透過公司通話] 的使用者無法使用委派、小組通話或回應群組功能。
    
- [透過公司通話] 的使用者無法使用商務用 Skype 錄製會議、將通話設為靜音或取消靜音、保留或轉接通話，或使用通話駐留。
    
- 使用者無法透過 [呼叫] 使用通話來存取其 PBX 語音信箱訊息。
    
- 透過工作進行通話的使用者無法將開始進行語音通話的會話升級為包含視頻、Powerpoint、白板或一個筆記等通訊的合作會議。
    
- [透過工作通話的使用者] 無法將更多使用者新增至兩人通話。
    
- 不支援 deskphone 配對或 VDI 外掛程式配對。
    
- 如果使用者使用 PBX 電話撥打或接聽電話（而不是使用商務用 Skype 視窗），就不會有通話記錄。
    
- 如果您的 PBX 系統不支援**參照取代**，則會發生下列行為。 透過 [通話通話] 時，如果使用者從 PBX 手機傳送正在進行的通話，通話視窗就不會從商務用 Skype 視窗中消失。 如果使用者接著關閉通話視窗，則傳送目標與 transferee 之間的呼叫將會結束。 
    
## <a name="prerequisites-for-call-via-work"></a>透過工作進行通話的先決條件

若要讓任何使用者都能透過工作撥打電話，您必須準備好一些必備的功能。 如需這些必備元件的詳細資訊，以及如何讓使用者使用商務用 Skype Server 2015 來通話的相關步驟，請參閱在[商務用 Skype Server 中部署通話](../../deploy/deploy-call-via-work.md)。 
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype 中規劃遠端通話控制](remote-call-control.md)
  
[部署商務用 Skype Server 2015 的從公司撥號功能](../../deploy/deploy-call-via-work.md)

