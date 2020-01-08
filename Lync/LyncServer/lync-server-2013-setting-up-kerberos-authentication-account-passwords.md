---
title: Lync Server 2013：設定 Kerberos 驗證帳戶密碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ca8bf5d1b3dc90b1ceacbe581e0426b5c0aaa9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Kerberos 驗證帳戶密碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010-11-03_

在您建立 Kerberos 驗證帳戶的電腦物件之後，您可以設定帳戶的密碼。 您可以執行 Windows PowerShell Cmdlet，在一台伺服器上設定 Kerberos 帳戶密碼。 您可以在針對 Kerberos 驗證建立的物件上設定密碼。 密碼可以設定為已知的值，但預設為隨機密碼。 使用該帳戶的所有 Kerberos 驗證來源都可使用此密碼。 您可以使用 Windows PowerShell Cmdlet 來設定和管理 Kerberos 帳戶密碼。

<div>


> [!NOTE]  
> Kerberos 帳戶物件是電腦物件，但在所參照的 Windows PowerShell Cmdlet 中使用 UserAccount 參數來進行操作。 請注意，這不是錯誤，但在與 Kerberos 帳戶建立和維護搭配使用時的預期行為。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中於伺服器上設定 Kerberos 驗證帳戶密碼](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [在 Lync Server 2013 中同步處理 Kerberos 驗證帳戶密碼至 IIS](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

