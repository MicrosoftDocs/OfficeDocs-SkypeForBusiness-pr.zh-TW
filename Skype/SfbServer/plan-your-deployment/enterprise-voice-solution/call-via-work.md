---
title: 規劃商務用 Skype Server 中的工作通話
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 規劃在商務用 Skype Server 中的工作進行呼叫，可在商務用 Skype 和 pbx 電話系統之間進行整合，讓使用者可以使用商務用 Skype 來控制其 PBX 電話。
ms.openlocfilehash: 268ee3a6caa7b304cc63b4e7e16c2a7565f9ced3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768561"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>規劃商務用 Skype Server 中的工作通話
 
規劃在商務用 Skype Server 中的工作進行呼叫，可在商務用 Skype 和 pbx 電話系統之間進行整合，讓使用者可以使用商務用 Skype 來控制其 PBX 電話。
  
 「透過 **公司通話**」是商務用 Skype Server 中的新功能，可讓您將商務用 Skype 解決方案與現有的 PBX 電話系統整合。 啟用通過工作呼叫的使用者可以按一下商務用 Skype，撥打您的部署或外部使用者的其他使用者。 使用使用者的 PBX 電話完成通話。 這可讓使用 PBX 電話的使用者在其豐富的商務用 Skype 交談中包含音訊。 在舊版的 Lync Server 遠端呼叫控制中，有一個功能可讓使用者透過 Lync Server 控制其 PBX 電話。 在商務用 Skype Server 中，此功能已由「透過運作」的呼叫取代。
  
透過公司通話為 PBX 電話使用者啟用下列各項
  
- 隨選即用經驗，透過 PBX 電話提供音訊。
    
- 目前狀態、使用者搜尋和 IM 整合--例如，IM 會話中的兩個透過工作使用者撥打的電話，都可以透過 PBX 電話提供音訊，將音訊新增至其會話。
    
- 透過「工作通話」新增 IM、應用程式共用和檔案傳輸的功能。
    
- 按一下一次會議加入功能
    
## <a name="how-it-works"></a>運作方式

「透過公司通話」使用整合通訊網頁 API (UCWA) 作為後端至後端使用者代理程式 (pbx 系統與您的商務用 Skype Server 部署之間) ，因此，您必須使用電腦不支援的電信應用程式 (CSTA) 閘道才能連接商務用 Skype Server 與 PBX 系統。 UCWA 是先前版本的 Lync Server 所引進的服務，可與行動裝置和 web 用戶端進行連線，並且會自動安裝在每一部前端伺服器上。
  
### <a name="call-workflow-for-a-call-via-work-call"></a>通話工作流程以供通話通話

以下說明如何啟用透過工作呼叫的使用者可以使用商務用 Skype Server 進行通話：
  
![顯示通話通話期間的步驟。首先，來電者會按一下呼叫商務用 Skype 用戶端中的某人;然後，UCWA 會振鈴來電者的電話。 當來電者挑選電話時，會呼叫收件者。](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. 使用者在其商務用 Skype 用戶端中選取使用者，然後按一下電話圖示進行呼叫。 或者，在 IM 交談期間，使用者按一下以撥打與其有會話的使用者。
    
2. 撥打通話之使用者的 PBX 電話會開始振鈴。 此電話的來電者識別碼會顯示您已設定為透過通話通話撥打的所有使用者的來電者識別碼中所設定的全域電話號碼。 此通用電話號碼不是對應于任何一位人員電話的實際電話號碼。 相反地，這是一種視覺信號，可讓使用者知道這是自己的撥出電話，而不是在同一時間發生來電。 當您從公司部署通話時，應教育這些使用者關於此通用電話號碼及其意義。
    
3. 撥打電話的使用者會拾取其 PBX 電話。 商務用 Skype 然後初始化呼叫者的語音通話。 
    
4. 受話者的答案是由語音電話開始。 如果兩位使用者已有 IM 會話，則可以繼續。
    
### <a name="joining-a-conference-with-call-via-work"></a>加入會議，並透過公司通話

透過使用者的來電可以按一下會議 URL 來加入排程的會議。 商務用 Skype 然後顯示 **撥出至** 郵件，直到會議服務撥打使用者的 PBX 電話。 「透過公司來電」使用者接著挑選 PBX 電話並加入會議。
  
「透過公司通話」使用者也可以使用商務用 Skype 中的 [**立即開會**] 選項來建立 [立即開會] 會議。 然後，使用者會看到 **撥號到** 郵件，以及 PBX 電話響起。
  
透過使用者的通話也可以從商務用 Skype 中呼叫會議 Bridge 號碼，撥打會議。 如果需要會議 PIN，使用者必須使用 PBX 電話來輸入 PIN 碼。
  
### <a name="incoming-calls"></a>來電

當啟用透過工作呼叫的使用者收到商務用 Skype 呼叫時，PBX 電話和使用者的商務用 Skype 用戶端會同時 (所有的振鈴，如果使用者已設定同時振鈴) 。 使用者可以透過挑選 PBX 電話或在商務用 Skype 通知上按一下 [**接受**] 來接受通話。 如果使用者接受使用商務用 Skype 的呼叫，則通話的商務用 Skype 視窗會保持開啟狀態。 不過，如果使用者透過接聽 pbx 電話接受通話，則商務用 Skype 通知視窗會關閉，而且沒有商務用 Skype 會話，只是透過 PBX 電話進行語音通話。
  
當啟用透過工作呼叫的使用者接到 PBX 呼叫時，則只會使用 PBX 電話的環。
  
## <a name="limitations-of-call-via-work"></a>從公司通話的限制

「透過公司通話」是一個語音解決方案，只需要硬體安裝，但與完整企業語音或遠端呼叫控制中可用的功能有限制。 透過工作呼叫的限制如下：
  
- 如果透過公司的來電已設定來電轉接至透過工作來電號碼的來電，而某人嘗試將此使用者邀請使用者的電話號碼給會議，邀請將不會到達使用者。 您應教育使用者按一下名稱，而非電話號碼，以邀請參與者加入會議。 
    
- 從公司通話通話時，增強型911功能和惡意呼叫追蹤無法使用。
    
- 啟用透過工作呼叫的使用者無法使用委派、小組通話或回應群組功能。
    
- 「透過公司通話」的使用者無法使用商務用 Skype 錄製會議、靜音或取消靜音通話、保留或轉接通話，或使用通話駐留。
    
- 使用者無法使用「透過運作呼叫」存取其 PBX 語音訊息。
    
- 「透過運作的來電使用者」無法將開始語音電話的會話提升為包含諸如影片、Powerpoint、白板或一個附注等通訊的合作會議。
    
- 「從公司通話」的使用者無法將更多使用者新增至2人通話。
    
- 不支援 deskphone 配對或 VDI 外掛程式配對。
    
- 如果使用者使用 PBX 電話撥打或接聽電話 (但未使用商務用 Skype 視窗) ，則不會有通話記錄。
    
- 如果您的 PBX 系統不支援 **參照取代**，將會發生下列行為。 在透過工作通話通話時，如果使用者從 PBX 電話轉接進行中的呼叫，[呼叫] 視窗將不會從其商務用 Skype 視窗中消失。 如果使用者接著關閉通話視窗，則傳送目標與 transferee 之間的呼叫會結束。 
    
## <a name="prerequisites-for-call-via-work"></a>從公司通話的必要條件

若要讓任何使用者都能撥打工作，您必須預先準備一些必要條件。 如需這些必要條件的詳細資訊，以及如何讓使用者能夠透過工作進行通話的步驟，請參閱[商務用 Skype Server 2015 中的「部署呼叫](../../deploy/deploy-call-via-work.md)」。 
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype 中規劃遠端呼叫控制](remote-call-control.md)
  
[從商務用 Skype Server 2015 的工作部署通話](../../deploy/deploy-call-via-work.md)

