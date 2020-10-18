---
title: Lync Server 2013：設定 Kerberos 驗證帳戶密碼
description: Lync Server 2013：設定 Kerberos 驗證帳戶密碼。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614b1411f9454c39843f4e69cabbfc3b02986e51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577219"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Kerberos 驗證帳戶密碼

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010-11-03_

在您為 Kerberos 驗證帳戶建立電腦物件之後，您可以設定該帳戶的密碼。 在一部伺服器上執行 Windows PowerShell Cmdlet 以設定 Kerberos 帳戶密碼。 您可以在您為 Kerberos 驗證建立的物件上設定密碼。 密碼可以設定為已知值，但預設為隨機密碼。 密碼可用於所有使用該帳戶的 Kerberos 驗證來源。 您可以使用 Windows PowerShell Cmdlet 來設定及管理 Kerberos 帳戶密碼。

<div>


> [!NOTE]  
> Kerberos account 物件是電腦物件，但是會將 UserAccount 參數用於所參照 Windows PowerShell Cmdlet 中的 operations。 請注意，這不是錯誤，但搭配 Kerberos 帳戶建立及維護使用時的預定行為。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中的伺服器上設定 Kerberos 驗證帳戶密碼](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [在 Lync Server 2013 中同步處理 Kerberos 驗證帳戶密碼至 IIS](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

