---
title: Lync Server 2013：設定 Kerberos 驗證
description: Lync Server 2013：設定 Kerberos 驗證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb461968bc073edbfe640f609257f3e84c192461
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577229"
---
# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Kerberos 驗證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

Lync Server 2013 支援 Web 服務的 NTLM 和 Kerberos 驗證。 Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 使用預設的 RTCComponentService 和 RTCService 作為使用者帳戶，以執行 Web 服務應用程式集區，讓服務主體名稱 (SPN) 指派給使用者帳戶，並作為驗證主體。 Lync Server 會使用 NetworkService 來執行 Web 服務，且 NetworkService 不能有指派給它的 Spn。

為了解決未讓 Active Directory 物件保留 Spn 的問題，Lync Server 控制台可以使用電腦帳戶物件來進行此專案的。 電腦帳戶物件可以保留 Spn，但不受密碼到期的限制，這是在舊版中使用使用者帳戶時發生的問題。

您可以使用 Windows PowerShell Cmdlet 來設定電腦物件，以提供 Kerberos 驗證。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中啟用 Kerberos 驗證的先決條件](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [在 Lync Server 2013 中建立 Kerberos 驗證帳戶](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [在 Lync Server 2013 中指派 Kerberos 驗證帳戶至網站](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [在 Lync Server 2013 中設定 Kerberos 驗證帳戶密碼](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [在 Lync Server 2013 中，新增 Kerberos 驗證至其他網站](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [在 Lync Server 2013 中，移除網站的 Kerberos 驗證](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [在 Lync Server 2013 中測試和報告 Kerberos 驗證的狀態和指派](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

