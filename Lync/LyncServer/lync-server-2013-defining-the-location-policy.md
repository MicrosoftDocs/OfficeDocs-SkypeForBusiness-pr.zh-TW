---
title: Lync Server 2013：定義位置原則
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
ms.openlocfilehash: 8bdb3b556f5b9a8d552a3c48e300b8c4b7b19f5f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504520"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a>定義 Lync Server 2013 的位置原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

每個位置原則都包含下列資訊：

  - **已啟用緊急服務**  
    當這個值為 **[是]** 時，用戶端會啟用 E9-1-1。 當用戶端註冊時，它會嘗試從 Location 資訊服務取得位置，並將位置資訊包含在緊急通話的一部分中。

<!-- end list -->

  - **需要位置**  
    只有當**啟用的服務**   設定為 **[是]** 時，才使用此設定。
    
    您可以設定 [ **必要的位置** ] 設定以定義用戶端行為。 將值設為 [ **否** ] 表示將不會提示使用者輸入位置。 將值設為 **[是]** ，表示系統會提示使用者輸入位置，但可以關閉提示。 將值設定為 **免責聲明** 表示會提示使用者輸入位置，而且會在使用者嘗試消除提示時顯示免責聲明。 在所有情況下，使用者都可以繼續使用用戶端。
    
    <div>
    

    > [!NOTE]  
    > 若使用者在啟用 E9-1-1 前手動輸入位置，將不會顯示免責聲明文字。 已查看免責聲明的使用者將不會查看免責聲明文字的更新。

    
    </div>

<!-- end list -->

  - **增強型緊急服務免責聲明**  
    此設定指定使用者在其取消提示的位置時所看到的免責聲明。 在 Lync Server 2013 中，您可以使用位置原則為不同的地區設定或不同的使用者集合設定不同的免責聲明。
    
    <div>
    

    > [!NOTE]  
    > 此位置原則設定與 Lync Server 2010 不同，您可以使用 <STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> Cmdlet 來設定整個組織的全域免責聲明。 若全域免責聲明已存在，您必須在位置原則中指定該免責聲明。 也就是說，Lync Server 2013 只會使用在位置原則中指定的免責聲明。

    
    </div>

<!-- end list -->

  - **緊急撥號字串**  
    此撥號字串 (較少的前置 "+"，但包括 Lync 使用者撥號對應表所執行的任何正規化) 表示通話是緊急通話。 [ **緊急撥號] 字串** 會使用戶端在通話中包含位置和回呼資訊。
    
    <div>
    

    > [!NOTE]  
    > 如果您的組織未使用外部線路存取首碼，您不需要建立對應的撥號對應表正規化規則，在將呼叫傳送至 Lync 集區伺服器上的輸出路由之前，將 "+" 新增至911字串;「+」會因位置原則而自動加上 Lync 用戶端。 不過，如果您的網站使用外部存取前置詞，您必須將正規化規則新增至適用的撥號對應表原則，以去掉外部存取前置詞並新增 "+"。 例如，如果您的位置使用外部存取前置詞9，而且使用者可撥打 9 &nbsp; 911 來進行緊急通話，用戶端會使用其撥號對應表原則，在來電者位置設定檔中的路由評估撥號號碼之前，先將此值與 + 911 進行正常化。

    
    </div>

<!-- end list -->

  - **緊急撥號字串遮罩**  
    以分號分隔的撥號字串清單，可轉譯成指定的 **緊急撥號字串**。 例如，您可能想要新增112，也就是歐洲大多數的緊急服務號碼。 從歐洲取得的 Lync 使用者可能不會知道911是美國的緊急電話號碼，但可以撥打112並取得相同的結果。 如使用緊急撥號字串，請勿在每個號碼前加上 "+"，而且如果您使用外部行存取碼，請確定使用者的撥號對應表原則中有正規化規則可去掉存取碼位。

<!-- end list -->

  - **PSTN 使用方式**  
    PSTN 使用方式的名稱，此介面包含決定 SIP 主幹、PSTN 閘道或 ELIN 閘道緊急通話將前往的路由路徑。
    
    <div>
    

    > [!NOTE]  
    > 一個位置原則只能有一個可用的使用方式。 這種 PSTN 使用方式會覆寫指派給使用者語音原則的 PSTN 使用方式，但是只適用于撥入緊急撥號字串或其中一個緊急撥號字串遮罩的來電。

    
    </div>

<!-- end list -->

  - **通知 URI**  
    指定在進行緊急通話時，接收立即訊息 (IM) 通知的安全性人員一或多個 SIP URIs。 支援通訊群組。

<!-- end list -->

  - **會議 URI**  
    指定「直接向內撥號 (已) 號碼 (通常是) 的安全性服務台號碼，應警衛在緊急通話時進行此設定。

<!-- end list -->

  - **會議模式**  
    指定是否要使用單向或雙向通訊，將會議 URI 警衛至緊急通話。

<!-- end list -->

  - **位置重新整理間隔**  
    指定從位置資訊服務之位置更新之用戶端要求 (的時間) （以小時為單位）。 此值可設為1到12之間的任何值。 預設值為 4。

</div>

<span> </span>

</div>

</div>

</div>

