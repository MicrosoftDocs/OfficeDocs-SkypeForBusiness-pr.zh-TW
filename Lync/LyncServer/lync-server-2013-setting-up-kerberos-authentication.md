---
title: Lync Server 2013： 設定 Kerberos 驗證
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
ms.openlocfilehash: 42f2c781b01aaa1ac00793f97067f24233c1e8db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>設定 Lync Server 2013 中的 Kerberos 驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

Lync Server 2013 支援 NTLM 和 Kerberos 驗證的 Web 服務。 Office Communications Server 2007 和 Office Communications Server 2007 R2 做為預設 RTCComponentService 和 RTCService 的使用者帳戶來執行 Web 服務應用程式集區，指派給使用者，讓服務主體名稱 (SPN)帳戶和做為驗證主體。 Lync Server 會使用 NetworkService 若要執行 Web 服務和 NetworkService 不能有指派給它的 Spn。

若要解決問題： 不保留 Spn 的 Active Directory 物件，Lync Server Control Panel 可以達到此目的使用電腦 account 物件。 電腦帳戶物件可以保留的 Spn，並不會受到密碼到期，已使用在舊版中的使用者帳戶的問題。

您可以使用 Windows PowerShell cmdlet 來設定電腦物件，以提供 Kerberos 驗證。

<div>

## <a name="in-this-section"></a>本章節內容

  - [啟用 Lync Server 2013 中的 Kerberos 驗證的必要條件](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [在 Lync Server 2013 中建立的 Kerberos 驗證帳戶](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [將 Kerberos 驗證帳戶指派給 Lync Server 2013 中的網站](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [設定 Lync Server 2013 中的 Kerberos 驗證帳戶密碼](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Lync Server 2013 中將 Kerberos 驗證新增到其他站台](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Lync Server 2013 中從網站移除 Kerberos 驗證](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [測試和報告 [狀態] 和 [工作分派的 Lync Server 2013 中的 Kerberos 驗證](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

