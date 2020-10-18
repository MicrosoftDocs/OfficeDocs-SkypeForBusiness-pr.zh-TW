---
title: Lync Server 2013：保護 IIS
description: Lync Server 2013：保護 IIS。
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
ms.openlocfilehash: 51161f221c7235aad04850fdccc5d5e9db5cb579
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579729"
---
# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="5f383-103">在 Lync Server 2013 中保護 IIS</span><span class="sxs-lookup"><span data-stu-id="5f383-103">Protecting IIS in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f383-104">_**主題上次修改日期：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="5f383-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="5f383-105">在 Microsoft Office 通訊伺服器2007和 Microsoft Office 通訊伺服器 2007 R2 中，Internet Information Services (IIS) 是在標準使用者帳戶下執行。</span><span class="sxs-lookup"><span data-stu-id="5f383-105">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="5f383-106">這可能會導致問題：如果該密碼過期，您會失去 Web 服務，通常這是很難診斷的問題。</span><span class="sxs-lookup"><span data-stu-id="5f383-106">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="5f383-107">為了協助避免密碼到期的問題，Microsoft Lync Server 2013 可讓您為不) 存在的電腦建立電腦帳戶 (，而該電腦可以充當執行 IIS 之網站中所有電腦的驗證主體。</span><span class="sxs-lookup"><span data-stu-id="5f383-107">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="5f383-108">因為這些帳戶使用 Kerberos 驗證通訊協定，所以帳戶稱為 Kerberos 帳戶，新驗證處理序別名 Kerberos Web 驗證。</span><span class="sxs-lookup"><span data-stu-id="5f383-108">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="5f383-109">這樣可讓您使用單一帳戶來管理所有 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="5f383-109">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="5f383-110">若要在此驗證主體下執行伺服器，您必須先使用 New-CsKerberosAccount Cmdlet 建立一個電腦帳戶；然後此帳戶會指派給一或多個站台。</span><span class="sxs-lookup"><span data-stu-id="5f383-110">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="5f383-111">進行指派之後，會透過執行 Enable-CsTopology Cmdlet 來啟用帳戶與 Lync Server 2013 網站之間的關聯。</span><span class="sxs-lookup"><span data-stu-id="5f383-111">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="5f383-112">除此之外，這也會在 Active Directory 網域服務 (AD DS) 中建立必要的服務主體名稱 (SPN)。</span><span class="sxs-lookup"><span data-stu-id="5f383-112">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="5f383-113">SPN 提供讓用戶端應用程式能夠找到特定服務的方式。</span><span class="sxs-lookup"><span data-stu-id="5f383-113">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="5f383-114">如需詳細資訊，請參閱作業文件中的＜[New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount)＞。</span><span class="sxs-lookup"><span data-stu-id="5f383-114">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="5f383-115">最佳作法</span><span class="sxs-lookup"><span data-stu-id="5f383-115">Best Practices</span></span>

<span data-ttu-id="5f383-p103">為幫助增加 IIS 的安全性，建議您為 IIS 實作 Kerberos 帳戶。如果您不實作 Kerberos 帳戶，IIS 會在標準使用者帳戶之下執行。</span><span class="sxs-lookup"><span data-stu-id="5f383-p103">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS. If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

