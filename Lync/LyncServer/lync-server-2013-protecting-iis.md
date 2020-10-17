---
title: Lync Server 2013：保護 IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aae84d208df1d7c2945fee641b243bf7110902c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513190"
---
# <a name="protecting-iis-in-lync-server-2013"></a>在 Lync Server 2013 中保護 IIS

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-05_

在 Microsoft Office 通訊伺服器2007和 Microsoft Office 通訊伺服器 2007 R2 中，Internet Information Services (IIS) 是在標準使用者帳戶下執行。 這可能會導致問題：如果該密碼過期，您會失去 Web 服務，通常這是很難診斷的問題。 為了協助避免密碼到期的問題，Microsoft Lync Server 2013 可讓您為不) 存在的電腦建立電腦帳戶 (，而該電腦可以充當執行 IIS 之網站中所有電腦的驗證主體。 因為這些帳戶使用 Kerberos 驗證通訊協定，所以帳戶稱為 Kerberos 帳戶，新驗證處理序別名 Kerberos Web 驗證。 這樣可讓您使用單一帳戶來管理所有 IIS 伺服器。

若要在此驗證主體下執行伺服器，您必須先使用 New-CsKerberosAccount Cmdlet 建立一個電腦帳戶；然後此帳戶會指派給一或多個站台。 進行指派之後，會透過執行 Enable-CsTopology Cmdlet 來啟用帳戶與 Lync Server 2013 網站之間的關聯。 除此之外，這也會在 Active Directory 網域服務 (AD DS) 中建立必要的服務主體名稱 (SPN)。 SPN 提供讓用戶端應用程式能夠找到特定服務的方式。 如需詳細資訊，請參閱作業文件中的＜[New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount)＞。

<div>

## <a name="best-practices"></a>最佳作法

為幫助增加 IIS 的安全性，建議您為 IIS 實作 Kerberos 帳戶。如果您不實作 Kerberos 帳戶，IIS 會在標準使用者帳戶之下執行。

</div>

</div>

<span> </span>

</div>

</div>

</div>

