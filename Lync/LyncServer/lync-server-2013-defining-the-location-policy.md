---
title: Lync Server 2013： 定義位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64c164f24f0f2c140a140b7343dd526979cc2bff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>定義 Lync Server 2013 的位置原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-29_

每個位置原則都包含下列資訊：

  - **已啟用緊急服務**  
    當此值為 [**是**] 時，用戶端會啟用 E9-1-1。 當用戶端登錄時，它會嘗試取得從位置資訊服務的位置，且會包含一部分緊急電話的位置資訊。

<!-- end list -->

  - **必要位置**  
    使用此設定僅當**已啟用緊急服務** 設為 [**是]**。
    
    您可以設定**位置所需**的設定，可定義的用戶端行為。 將值設定為 [**否]** 表示位置不會提示使用者。 設定為 **[是]** 的值表示使用者位置]，系統會提示，但可以解除提示。 設定**免責聲明**的值表示使用者會提示的位置，並且也會顯示免責聲明如果使用者嘗試解除提示。 在所有情況下，使用者可以繼續使用用戶端。
    
    <div>
    

    > [!NOTE]  
    > 如果使用者手動輸入位置之前要啟用 E9-1-1，將不會出現免責聲明文字。 更新至免責聲明的文字不會檢視的檢視已經過免責聲明的使用者。

    
    </div>

<!-- end list -->

  - **增強型緊急服務免責聲明**  
    此設定指定免責聲明，如果他們關閉位置的提示，請參閱 < 的使用者。 在 Lync Server 2013 中，您可以使用位置原則來設定不同的免責聲明，不同地區設定或不同組的使用者。
    
    <div>
    

    > [!NOTE]  
    > 此位置原則設定與 Lync Server 2010]，其中您用於<STRONG>Set-cssipresponsecodetranslationrule</STRONG>指令程式設定為整個組織的全域免責聲明。 如果全域免責聲明已經存在，您需要在 [位置原則中指定該免責聲明。 也就是說，Lync Server 2013 使用位置原則中指定的免責聲明。

    
    </div>

<!-- end list -->

  - **緊急撥號字串**  
    此撥號對應表的字串 (小於前置 「 + 」，但包括由 Lync 使用者的撥號對應表規劃完成任何正規化) 表示通話時，緊急通話。 **緊急撥號字串**會導致用戶端包括位置和使用呼叫的回撥資訊。
    
    <div>
    

    > [!NOTE]  
    > 如果您的組織不使用外部線路存取首碼，您不需要建立對應的撥號對應表正規化規則，新增 「 + 」 之前傳送的呼叫輸出路由 Lync 集區伺服器; 上 911 字串「 + 」 會自動加在 Lync 用戶端，因為位置原則。 不過，如果您的網站使用的外部存取首碼，您需要新增正規化規則至適用的撥號對應表原則階梯狀往外部存取首碼，並加入 「 + 」。 例如，如果您的位置使用為 9 和使用者外部存取首碼撥 9&nbsp;911 來撥打緊急通話，用戶端會使用其撥號對應表原則正規化的需求，這要 +911 之前撥打的號碼評估的發話者的位置設定檔中的路由。

    
    </div>

<!-- end list -->

  - **緊急撥號字串遮罩**  
    以分號分隔清單的撥號對應表字串會轉譯成**緊急撥號字串**所指定。 例如，可能會想要新增 112，這是大部分的歐洲的緊急服務號碼。 造訪 Lync 使用者從歐洲可能不知道要 911 是美國緊急電話號碼，但他們可以撥 112 並得到相同結果。 為與緊急撥號字串，不含"+"之前每一個數字，而且如果您使用外部線路存取碼時，務必要存取程式碼數字中移除使用者的撥號對應表原則中有正規化規則。

<!-- end list -->

  - **PSTN 使用方式**  
    包含的路由路徑可決定哪一個 SIP 主幹、 PSTN 閘道或 ELIN 閘道緊急通話將會移至 [PSTN 使用方式的名稱。
    
    <div>
    

    > [!NOTE]  
    > 只有一個流量可以指派給位置原則。 此 PSTN 使用方式會覆寫指派給使用者的語音原則、 PSTN 使用方式，但僅適用於緊急撥號字串或下列其中一個緊急撥號字串遮罩撥打。

    
    </div>

<!-- end list -->

  - **通知 URI**  
    指定的安全性人員接收立即訊息 (IM) 通知時撥打緊急電話的一或多個 SIP Uri。 支援的通訊群組。

<!-- end list -->

  - **會議 URI**  
    會指定應該是警衛室時撥打緊急電話直接向內撥號 (DID) 號碼 （通常是安全性 desk 號碼）。

<!-- end list -->

  - **會議模式**  
    會指定如果會議 URI 是否將警衛緊急通話使用單向或雙向通訊。

<!-- end list -->

  - **位置重新整理間隔**  
    從 [位置資訊服務的位置更新的用戶端要求之間指定的時間 （以小時為單位）。 值可以設定為任何介於 1 到 12。 預設值為 4。

</div>

<span> </span>

</div>

</div>

</div>

