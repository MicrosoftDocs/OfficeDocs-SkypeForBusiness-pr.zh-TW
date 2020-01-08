---
title: 設定 XMPP 閘道存取原則及憑證
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 022d396d9d87b0112a24d06ee6a863f98795dec8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40978282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>設定 XMPP 閘道存取原則及憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

XMPP 同盟會根據可擴展訊息和目前狀態通訊協定（XMPP）來定義外部部署。 XMPP 設定可讓 Lync 使用者透過以下方式存取 XMPP 網域使用者：

  - IM 和目前狀態-僅限人員的人員

  - 在 Lync 用戶端中建立 XMPP 同盟連絡人

當您針對可擴展訊息和目前狀態通訊協定（XMPP）同盟合作夥伴支援策略時，這些原則會套用至 XMPP 聯盟網域的使用者，但不會套用至會話初始通訊協定（SIP）立即訊息（IM）服務提供者的使用者（例如，Windows Live）或 SIP 聯盟網域。 您可以針對每個 XMPP 聯盟網域設定 XMPP 聯盟夥伴，以允許使用者新增連絡人並與之通訊。 原則就緒之後，您必須設定 XMPP 閘道憑證。

<div>


> [!NOTE]  
> 若要開始 XMPP 閘道遷移，您需要部署 Lync Server 2013 XMPP 閘道，並設定存取原則，以讓 Lync Server 2013 的使用者能夠 XMPP 閘道。 在執行這些步驟之前，必須先將所有使用者移至 Lync Server 2013 部署。 如需詳細資訊，請參閱<A href="configure-xmpp-gateway-on-lync-server-2013.md">在 Lync Server 2013 上設定 XMPP 閘道</A>。



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>設定外部存取原則，以允許使用者使用 Lync Server 2013 XMPP 閘道

1.  開啟 [Lync Server 控制台]。

2.  在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [**外部存取原則**]。

3.  按一下 [**新增**]，然後按一下 [**使用者原則**]。

4.  輸入外部存取使用者原則的名稱。

5.  提供外部存取使用者原則的描述。

6.  選取 [**啟用與聯盟使用者的通訊**]。

7.  選取 [**啟用與 XMPP 聯盟使用者的通訊**]。

8.  按一下 [**認可**]，儲存您對網站或使用者原則所做的變更。

</div>

</div>

<span> </span>

</div>

</div>

</div>

