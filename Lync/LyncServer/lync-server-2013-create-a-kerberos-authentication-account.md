---
title: Lync Server 2013： 建立 Kerberos 驗證帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e59703328fad7c8763bc1a6cc018c2cbc585c3ed
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>在 Lync Server 2013 中建立的 Kerberos 驗證帳戶

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-01-02_

若要順利完成此程序，則最少應該以 Domain Admins 群組成員的身分登入伺服器或網域。

您可以建立每個網站的 Kerberos 驗證帳戶，也可以建立單一 Kerberos 驗證帳戶，並將它用於所有網站。 您可以使用 Windows PowerShell cmdlet 來建立及管理的帳戶，包括用來識別指派給每個網站的帳戶。 拓撲產生器和 Lync Server 2013 控制台不要顯示 Kerberos 驗證帳戶。 使用下列程序，建立一或多個要用於進行 Kerberos 驗證的使用者帳戶。

<div>

## <a name="to-create-a-kerberos-account"></a>建立 Kerberos 帳戶

1.  以 Domain Admins 群組的成員，登入網域中執行 Lync Server 2013 或入已安裝系統管理工具的電腦的電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  從命令列中，執行下列命令：
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    例如：
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  開啟 [Active Directory 使用者和電腦] 確認已建立 [電腦] 物件，並展開 **[使用者]** 容器，然後確認使用者帳戶的 [電腦] 物件位在該容器內。

</div>

</div>

<span> </span>

</div>

</div>

</div>

