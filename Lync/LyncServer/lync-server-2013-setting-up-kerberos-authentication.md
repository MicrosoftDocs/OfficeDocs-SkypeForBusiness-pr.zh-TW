---
title: Lync Server 2013：設定 Kerberos 驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86526b40ee837866cdf0e3b016a8e4e627ca2eef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Kerberos 驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

Lync Server 2013 支援針對 Web 服務進行 NTLM 和 Kerberos 驗證。 Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 使用預設的 RTCComponentService 和 RTCService 作為使用者帳戶來執行 Web 服務應用程式池，允許將服務主體名稱（SPN）指派給使用者帳戶並充當驗證原則。 Lync Server 使用 NetworkService 來執行 Web 服務，而 NetworkService 不能指派 Spn 給它。

為了解決沒有 Active Directory 物件來保留 Spn 的問題，Lync Server [控制台] 可以使用電腦帳戶物件來達到此目的。 電腦帳戶物件可以保留 Spn，而且不受密碼到期的限制，這是在舊版中使用使用者帳戶的問題。

您可以使用 Windows PowerShell Cmdlet 來設定電腦物件，以提供 Kerberos 驗證。

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中啟用 Kerberos 驗證的先決條件](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [在 Lync Server 2013 中建立 Kerberos 驗證帳戶](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [在 Lync Server 2013 中將 Kerberos 驗證帳戶指派到網站](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [在 Lync Server 2013 中設定 Kerberos 驗證帳戶密碼](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [在 Lync Server 2013 中新增 Kerberos 驗證至其他站台](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [在 Lync Server 2013 中從網站移除 Kerberos 驗證](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [在 Lync Server 2013 中測試和報告 Kerberos 驗證的狀態和指派](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

