---
title: Lync Server 2013：來電者識別碼簡報
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24ca692dcfa4b2281fcb324c0f5fef5584b5a24e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508160"
---
# <a name="caller-id-presentation-in-lync-server-2013"></a>Lync Server 2013 中的呼叫者識別碼簡報

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

使用 Lync Server 2010 時，所叫方的電話號碼 (也就是說，稱為) 的電話號碼可以從 e.164 格式轉譯成主幹對等 (（即相關聯的閘道、專用交換機 (PBX) 或 SIP 主幹) ）所需的本機撥號格式。 若要執行此項作業，您必須定義一或多個轉譯規則，以在將其路由傳送至主幹對等之前轉譯要求 URI。

Lync Server 2013 引進的選項也可轉譯呼叫方的電話號碼 (也就是說，來電者撥打的電話號碼是由 e.164 格式) 所要求的，而這是主幹對等項所需的本機撥號格式。 例如，您可撰寫轉譯規則，來將撥號字串開頭的 +44 移除，並以 0144 來取代。

<div id="sectionSection0" class="section">

**使用 Lync Server 控制台設定來電者識別碼**

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[語音路由]**，然後按一下 **[主幹組態]**。

4.  在 **[主幹組態]** 頁面上，按兩下現有的主幹 (例如 **[通用]** 主幹)，顯示 **[編輯主幹組態]** 對話方塊。

5.  若要設定來電者 ID 呈現方式：
    
      - 若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。 在 **[來電號碼轉譯規則]** 中，按一下您想要與主幹建立關聯的規則，然後按一下 **[確定]**。
    
      - 若要定義新的轉譯規則並將其與主幹建立關聯，請按一下 **[新增]**。 如需定義新規則的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。
    
      - 若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。
    
      - 若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。 如需詳細資訊，請參閱 [在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。
    
    <div>
    

    > [!WARNING]  
    > 如果您已在相關聯的主幹對等上設定轉譯規則，則請勿將轉譯規則與主幹建立關聯，因為兩種規則可能會衝突。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

