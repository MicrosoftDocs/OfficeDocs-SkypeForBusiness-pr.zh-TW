---
title: Lync Server 2013：建立 Kerberos 驗證帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab4f93d4204f7ed1f2b22d27ddb51328f8330c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>在 Lync Server 2013 中建立 Kerberos 驗證帳戶

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-01-02_

若要成功完成此程式，您必須以網域管理員群組的成員的身分登入伺服器或網域。

您可以為每個網站建立 Kerberos 驗證帳戶，或者您可以建立單一 Kerberos 驗證帳戶並將它用於所有網站。 您可以使用 Windows PowerShell Cmdlet 來建立及管理帳戶，包括識別指派給每個網站的帳戶。 拓撲建立器和 Lync Server 2013 [控制台] 不會顯示 Kerberos 驗證帳戶。 使用下列程式建立一個或多個用來進行 Kerberos 驗證的使用者帳戶。

<div>

## <a name="to-create-a-kerberos-account"></a>建立 Kerberos 帳戶

1.  做為 Domain Admins 群組的成員，請登入執行 Lync Server 2013 的網域中的電腦，或登入安裝管理工具的電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  從命令列執行下列命令：
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    例如：
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  若要確認電腦物件是透過開啟 Active Directory 使用者和電腦來建立，請展開 [**使用者**] 容器，然後確認使用者帳戶的電腦物件位於容器中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

