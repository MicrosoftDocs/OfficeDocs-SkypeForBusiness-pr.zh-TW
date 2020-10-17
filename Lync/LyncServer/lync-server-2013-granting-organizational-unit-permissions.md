---
title: Lync Server 2013：授與組織單位許可權
description: Lync Server 2013：授與組織單位許可權。
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
ms.openlocfilehash: 47ad862241e409190620afa7dbf4fa73adf339de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554509"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中授與組織單位許可權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-05-14_

您可以使用 **Grant-CsOuPermission** 指令程式將許可權授與指定組織單位中的物件 (ou) ，使樹系準備建立的 RTC 通用群組成員可以存取，而不是 Domain Admins 群組的成員。 新增至指定 OU 的許可權與 **Enable-CsAdDomain** Cmdlet 會在網域準備期間新增至電腦和使用者容器的許可權相同。

使用 **Test-CsOuPermission** Cmdlet 來驗證您使用 **Grant-CsOuPermission** Cmdlet 所設定的許可權。

您可以使用 **Revoke-CsOuPermission** Cmdlet 來移除使用 **Grant-CsOuPermission** Cmdlet 所授與的許可權。

<div>

## <a name="to-grant-ou-permissions"></a>授與 OU 許可權

1.  在您想要授與 OU 許可權的網域中登入執行 Lync Server 2013 的電腦。 如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 參數，預設值為本機網域。

</div>

<div>

## <a name="to-verify-ou-permissions"></a>驗證 OU 許可權

1.  在您想要驗證您使用 **Grant-CsOuPermission** Cmdlet 所授與之 OU 許可權的網域中登入執行 Lync Server 2013 的電腦。 如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 參數，預設值為本機網域。

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>撤銷 OU 許可權

1.  在您要撤銷 **Grant-CsOuPermission** Cmdlet 所授與之 OU 許可權的網域中，登入執行 Lync Server 2013 的電腦。 如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 參數，預設值為本機網域。

</div>

</div>

<span> </span>

</div>

</div>

</div>

