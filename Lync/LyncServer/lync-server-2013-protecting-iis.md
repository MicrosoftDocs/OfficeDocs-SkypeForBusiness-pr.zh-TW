---
title: Lync Server 2013： 保護 IIS
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
ms.openlocfilehash: d53797c490ba53872786311b51e310e6400addf5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="92a1c-102">保護 Lync Server 2013 中的 IIS</span><span class="sxs-lookup"><span data-stu-id="92a1c-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92a1c-103">_**上次修改主題：** 2013年-12-05_</span><span class="sxs-lookup"><span data-stu-id="92a1c-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="92a1c-104">在 Microsoft Office Communications Server 2007 及 Microsoft Office Communications Server 2007 R2，網際網路資訊服務 (IIS) 執行標準的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="92a1c-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="92a1c-105">這可能會導致問題：如果該密碼過期，您會失去 Web 服務，通常這是很難診斷的問題。</span><span class="sxs-lookup"><span data-stu-id="92a1c-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="92a1c-106">若要協助避免發生過期密碼的問題，Microsoft Lync Server 2013 可讓您建立的電腦帳戶 （適用於實際上不存在的電腦），可以做為所有網站中執行的電腦 IIS 驗證主體。</span><span class="sxs-lookup"><span data-stu-id="92a1c-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="92a1c-107">因為這些帳戶使用 Kerberos 驗證通訊協定，所以帳戶稱為 Kerberos 帳戶，新驗證處理序別名 Kerberos Web 驗證。</span><span class="sxs-lookup"><span data-stu-id="92a1c-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="92a1c-108">這樣可讓您使用單一帳戶來管理所有 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="92a1c-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="92a1c-109">若要在此驗證主體下執行伺服器，您必須先使用 New-CsKerberosAccount Cmdlet 建立一個電腦帳戶；然後此帳戶會指派給一或多個站台。</span><span class="sxs-lookup"><span data-stu-id="92a1c-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="92a1c-110">工作分派之後，依執行 Enable-cstopology cmdlet 會啟用帳戶與 Lync Server 2013 網站之間的關聯。</span><span class="sxs-lookup"><span data-stu-id="92a1c-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="92a1c-111">除此之外，這也會在 Active Directory 網域服務 (AD DS) 中建立必要的服務主體名稱 (SPN)。</span><span class="sxs-lookup"><span data-stu-id="92a1c-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="92a1c-112">SPN 提供讓用戶端應用程式能夠找到特定服務的方式。</span><span class="sxs-lookup"><span data-stu-id="92a1c-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="92a1c-113">如需詳細資訊，請參閱作業文件中的＜[New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount)＞。</span><span class="sxs-lookup"><span data-stu-id="92a1c-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="92a1c-114">最佳作法</span><span class="sxs-lookup"><span data-stu-id="92a1c-114">Best Practices</span></span>

<span data-ttu-id="92a1c-p103">為幫助增加 IIS 的安全性，建議您為 IIS 實作 Kerberos 帳戶。如果您不實作 Kerberos 帳戶，IIS 會在標準使用者帳戶之下執行。</span><span class="sxs-lookup"><span data-stu-id="92a1c-p103">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS. If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

