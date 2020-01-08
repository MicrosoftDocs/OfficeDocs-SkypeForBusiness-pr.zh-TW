---
title: Lync Server 2013：保護 IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 711adaec00e37cbd826f8aabcadc45948548c3f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>在 Lync Server 2013 中保護 IIS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-05_

在 Microsoft Office 通訊伺服器2007和 Microsoft Office 通訊伺服器 2007 R2 中，網際網路資訊服務（IIS）是在標準使用者帳戶下執行。 這可能會造成問題：如果您的密碼已過期，可能會遺失您的 Web 服務，通常是難以診斷的問題。 為了協助避免密碼過期的問題，Microsoft Lync Server 2013 可讓您建立電腦帳戶（適用于不存在的電腦），可充當執行 IIS 之網站中所有電腦的驗證原則。 因為這些帳戶使用 Kerberos 驗證通訊協定，所以帳戶稱為 Kerberos 帳戶，而新的驗證處理序則稱為 Kerberos Web 驗證。 如此一來，您就能使用單一帳戶來管理所有 IIS 伺服器。

若要在這個驗證原則下執行伺服器，您必須先使用 CsKerberosAccount Cmdlet 建立電腦帳戶;這個帳戶就會指派給一或多個網站。 完成作業之後，您可以執行 CsTopology Cmdlet 來啟用帳戶和 Lync Server 2013 網站之間的關聯。 在其他專案中，這會在 Active Directory 網域服務（AD DS）中建立必要的服務主體名稱（SPN）。 SPN 讓用戶端應用程式能夠找到特定的服務。 如需詳細資訊，請參閱作業檔中的[新 CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) 。

<div>

## <a name="best-practices"></a>最佳做法

為了協助提高 IIS 的安全性，建議您為 IIS 實施 Kerberos 帳戶。 如果您沒有實現 Kerberos 帳戶，IIS 會在標準使用者帳戶下執行。

</div>

</div>

<span> </span>

</div>

</div>

</div>

