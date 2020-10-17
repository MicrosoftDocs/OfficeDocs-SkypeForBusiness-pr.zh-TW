---
title: 設定 XMPP 閘道的存取原則和憑證
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 870f55bc59ba5b3bed68545b54cbfcc341885162
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503210"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>設定 XMPP 閘道的存取原則和憑證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

XMPP 同盟會根據可延伸的訊息和顯示狀態通訊協定 (XMPP) 來定義外部部署。 XMPP 設定可讓 Lync 使用者依下列方式存取 XMPP 網域使用者：

  - IM 和目前狀態–僅限人員

  - 在 Lync 用戶端中建立 XMPP 同盟連絡人

當您設定支援可延伸訊息和目前狀態通訊協定 (XMPP) 同盟協力廠商的原則時，這些原則會套用至 XMPP 同盟網域的使用者，但不會套用至工作階段初始通訊協定 (SIP) 立即訊息 (IM) 服務提供者 (例如 Windows Live) 或 SIP 同盟網域的使用者。 您可以為每個 XMPP 同盟網域設定所需的 XMPP 同盟協力廠商，以讓使用者新增連絡人並與連絡人通訊。 原則就緒後，您必須設定 XMPP 閘道憑證。

<div>


> [!NOTE]  
> 若要開始 XMPP 閘道遷移，您必須部署 Lync Server 2013 XMPP 閘道，並設定存取原則以啟用 Lync Server 2013 XMPP 閘道的使用者。 在您執行這些步驟之前，必須先將所有使用者移至 Lync Server 2013 部署。 如需詳細資訊，請參閱 <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">CONFIGURE XMPP gateway On Lync Server 2013</A>。



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>設定外部存取原則，以啟用使用者的 Lync Server 2013 XMPP 閘道

1.  開啟 [Lync Server 控制台]。

2.  在左導覽列中，按一下 [ **同盟和外部存取**]，然後按一下 [ **外部存取原則**]。

3.  按一下 [ **新增** ]，然後按一下 [ **使用者原則**]。

4.  輸入外部存取使用者原則的名稱。

5.  提供外部存取使用者原則的描述。

6.  選取 [啟用與同盟使用者的通訊]****。

7.  選取 [啟用與 XMPP 同盟使用者的通訊]****。

8.  按一下 [認可]**** 以儲存對網站或使用者原則的變更。

</div>

</div>

<span> </span>

</div>

</div>

</div>

