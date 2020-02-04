---
title: Lync Server 2013：授與組織單位權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 084fb8cdebeda06d4441879f08f830021b65d2e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中授與組織單位權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-05-14_

您可以使用**Grant CsOuPermission** Cmdlet，在指定組織單位（ou）中授與物件的許可權，讓「林準備」所建立的 RTC 通用群組成員不會成為網域管理員群組的成員即可存取。 新增至指定 OU 的許可權與在網域準備期間， **Enable-CsAdDomain** Cmdlet 會新增到電腦和使用者容器的許可權相同。

使用**CsOuPermission** Cmdlet 來驗證您使用**Grant CsOuPermission** Cmdlet 設定的許可權。

您可以使用**Revoke CsOuPermission** Cmdlet 來移除您使用**Grant CsOuPermission** Cmdlet 所授予的許可權。

<div>

## <a name="to-grant-ou-permissions"></a>授與 OU 許可權

1.  在您想要授與 OU 許可權的網域中，登入執行 Lync Server 2013 的電腦。 如果組織單位位於不同的子域中，請使用屬於網域管理員群組或企業系統管理員群組成員的帳戶。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果您沒有指定 Domain 參數，則預設值為本地域。

</div>

<div>

## <a name="to-verify-ou-permissions"></a>驗證 OU 許可權

1.  在您想要驗證您使用**Grant CsOuPermission** Cmdlet 所授予的 OU 許可權之網域中，登入運行 Lync Server 2013 的電腦。 如果組織單位位於不同的子域中，請使用屬於網域管理員群組或企業系統管理員群組成員的帳戶。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果您沒有指定 Domain 參數，則預設值為本地域。

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>撤銷 OU 許可權

1.  在您想要吊銷**Grant CsOuPermission** Cmdlet 所授之 OU 許可權的網域中，登入執行 Lync Server 2013 的電腦。 如果組織單位位於不同的子域中，請使用屬於網域管理員群組或企業系統管理員群組成員的帳戶。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果您沒有指定 Domain 參數，則預設值為本地域。

</div>

</div>

<span> </span>

</div>

</div>

</div>

