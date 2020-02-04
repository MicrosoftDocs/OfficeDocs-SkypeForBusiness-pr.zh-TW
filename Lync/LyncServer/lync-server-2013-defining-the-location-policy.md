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
ms.openlocfilehash: feb7550412fa6cdcda3a8fc4dd9b7913912c34e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>定義 Lync Server 2013 的位置原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

每個位置原則都包含下列資訊：

  - **已啟用緊急服務**  
    如果此值為 **[是]**，則會為 E9-1-1 啟用用戶端。 用戶端註冊時，它會嘗試從位置資訊服務取得位置，並將位置資訊包含在緊急通話的一部分。

<!-- end list -->

  - **需要位置**  
    此設定僅在 [**啟用** 中的服務] 設定為 **[是]** 時使用。
    
    您可以設定**所需的位置**設定，以定義用戶端行為。 將此值設定為 [**否**] 表示系統不會提示使用者輸入位置。 將此值設定為 **[是]** 表示系統會提示使用者輸入位置，但可以關閉提示。 將此值設定為 [**免責聲明**] 表示系統會提示使用者輸入位置，而且在他們嘗試關閉提示時也會顯示免責聲明。 在任何情況下，使用者都可以繼續使用用戶端。
    
    <div>
    

    > [!NOTE]  
    > 如果使用者在啟用 E9 前手動輸入位置，則不會顯示免責聲明文字-1-1。 已查看免責聲明的使用者將不會看到免責聲明文字的更新。

    
    </div>

<!-- end list -->

  - **增強的緊急服務免責聲明**  
    此設定會指定使用者在關閉位置提示時所看到的免責聲明。 在 Lync Server 2013 中，您可以使用位置原則，針對不同的地區設定或不同的使用者集設定不同的免責聲明。
    
    <div>
    

    > [!NOTE]  
    > 這個位置原則設定與 Lync Server 2010 不同，您使用<STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> Cmdlet 來為整個組織設定全域免責聲明。 如果全域免責聲明已存在，您必須在位置原則中指定該免責聲明。 也就是說，Lync Server 2013 只使用位置原則中指定的免責聲明。

    
    </div>

<!-- end list -->

  - **緊急撥號字串**  
    這個撥號字串（較少前導 "+"，但包括 Lync 使用者的撥號計畫所完成的任何正常化）表示通話是緊急通話。 [**緊急撥號字串**] 會讓用戶端在通話中加入位置和回呼資訊。
    
    <div>
    

    > [!NOTE]  
    > 如果您的組織未使用外部線路存取首碼，您就不需要建立對應的撥號方案正常化規則，在將呼叫傳送到 Lync 伺服器上的輸出路由之前，將 "+" 新增至911字串;由於位置原則，Lync 用戶端將自動預先加上 "+"。 不過，如果您的網站使用外部存取前置詞，您必須將正常化規則新增到可分割外部存取前置詞的適用撥號方案原則，並新增 "+"。 例如，如果您的位置使用外部存取首碼9，且使用者要撥 9&nbsp;911 來撥打緊急電話，則用戶端將會使用撥號方案911原則，在撥打電話號碼之後，再由呼叫者的位置設定檔中的路由評估。

    
    </div>

<!-- end list -->

  - **緊急撥號字串遮罩**  
    以分號分隔的撥號字串清單，可翻譯成指定的**緊急撥號字串**。 例如，您可能會想要新增112，這是大多數歐洲的緊急服務號碼。 從歐洲造訪 Lync 使用者可能不知道911是美國的緊急電話號碼，但他們可以撥打112並取得相同的結果。 就像緊急撥號字串一樣，請不要在每個數位前加上 "+"，而且如果您使用外部線路存取代碼，請務必在使用者的撥號計畫原則中有正常化規則來剝離存取代碼位數。

<!-- end list -->

  - **PSTN 使用方式**  
    PSTN 使用的名稱，其中包含判斷哪些 SIP 幹線、PSTN 閘道或 ELIN 閘道緊急呼叫將前往的路由路徑。
    
    <div>
    

    > [!NOTE]  
    > 位置原則只能指派一個用法。 此 PSTN 使用會覆寫指派給使用者語音原則的 PSTN 使用量，但只適用于緊急撥號字串或其中一個緊急撥號字串遮罩的呼叫。

    
    </div>

<!-- end list -->

  - **通知 URI**  
    指定在發出緊急通話時接收立即訊息（IM）通知的安全性人員的一個或多個 SIP Uri。 支援通訊群組。

<!-- end list -->

  - **會議 URI**  
    指定在發出緊急通話時，應 conferenced 的直接向內撥號（已登錄）號碼（通常是安全服務台號碼）。

<!-- end list -->

  - **會議模式**  
    指定是否要使用單向或雙向通訊，將會議 URI conferenced 到緊急通話中。

<!-- end list -->

  - **位置重新整理間隔**  
    指定從位置資訊服務傳送位置更新之用戶端要求的時間長度（以小時為單位）。 這個值可以設定為1到12之間的任何值。 預設值為4。

</div>

<span> </span>

</div>

</div>

</div>

