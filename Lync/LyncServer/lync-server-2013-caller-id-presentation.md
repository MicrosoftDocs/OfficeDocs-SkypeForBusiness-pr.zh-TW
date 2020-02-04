---
title: Lync Server 2013：本機號碼簡報
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
ms.openlocfilehash: 2afe4682250bd6065ba368d7812dfdcd5626042e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a>Lync Server 2013 中的本機號碼簡報

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

使用 Lync Server 2010 時，呼叫方的電話號碼（也就是呼叫的電話號碼）可以從164格式翻譯成幹線對等（也就是相關閘道、私人分支 exchange （PBX）或 SIP 主幹）所需的本機撥號格式。 若要這樣做，您必須先定義一或多個翻譯規則，才能轉換要求 URI，然後再將它傳送到幹線對等。

Lync Server 2013 提供了選項，可將呼叫方的電話號碼（也就是呼叫者撥打的電話號碼）從 E-164 格式轉換為幹線對等所需的本機撥號格式。 例如，您可以撰寫翻譯規則，以從撥號字串開頭移除 + 44，然後將它取代為0144。

<div id="sectionSection0" class="section">

**使用 Lync Server [控制台] 設定本機號碼**

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。

4.  在 [**幹線**設定] 頁面上，按兩下現有的主幹（例如 [**全域**幹線]），以顯示 [**編輯主幹**設定] 對話方塊。

5.  若要設定本機號碼方式：
    
      - 若要從企業語音部署中所有可用的翻譯規則清單中選擇一或多個規則，請按一下 [**選取**]。 在 [**呼叫編號翻譯規則**] 中，按一下您要與主幹建立關聯的規則，然後按一下 **[確定]**。
    
      - 若要定義新的翻譯規則，並將其與骨幹建立關聯，請按一下 [**新增**]。 如需有關定義新規則的詳細資料，請參閱在部署檔中的[Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要編輯已經與主幹建立關聯的翻譯規則，請按一下規則名稱，然後按一下 [**顯示詳細資料**]。 如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 定義翻譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要複製現有的翻譯規則，以做為定義新規則的起點，請按一下規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。 如需詳細資訊，請參閱[在 Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要從主幹中移除翻譯規則，請將規則名稱醒目提示，然後按一下 [**移除**]。
    
    <div>
    

    > [!WARNING]  
    > 如果您已在關聯的中繼對等上設定翻譯規則，請不要將翻譯規則與幹線建立關聯，因為這兩個規則可能會衝突。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

