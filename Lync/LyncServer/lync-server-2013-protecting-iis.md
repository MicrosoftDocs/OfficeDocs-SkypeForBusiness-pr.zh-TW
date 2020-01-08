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

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="5cb96-102">在 Lync Server 2013 中保護 IIS</span><span class="sxs-lookup"><span data-stu-id="5cb96-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cb96-103">_**主題上次修改日期：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="5cb96-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="5cb96-104">在 Microsoft Office 通訊伺服器2007和 Microsoft Office 通訊伺服器 2007 R2 中，網際網路資訊服務（IIS）是在標準使用者帳戶下執行。</span><span class="sxs-lookup"><span data-stu-id="5cb96-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="5cb96-105">這可能會造成問題：如果您的密碼已過期，可能會遺失您的 Web 服務，通常是難以診斷的問題。</span><span class="sxs-lookup"><span data-stu-id="5cb96-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="5cb96-106">為了協助避免密碼過期的問題，Microsoft Lync Server 2013 可讓您建立電腦帳戶（適用于不存在的電腦），可充當執行 IIS 之網站中所有電腦的驗證原則。</span><span class="sxs-lookup"><span data-stu-id="5cb96-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="5cb96-107">因為這些帳戶使用 Kerberos 驗證通訊協定，所以帳戶稱為 Kerberos 帳戶，而新的驗證處理序則稱為 Kerberos Web 驗證。</span><span class="sxs-lookup"><span data-stu-id="5cb96-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="5cb96-108">如此一來，您就能使用單一帳戶來管理所有 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="5cb96-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="5cb96-109">若要在這個驗證原則下執行伺服器，您必須先使用 CsKerberosAccount Cmdlet 建立電腦帳戶;這個帳戶就會指派給一或多個網站。</span><span class="sxs-lookup"><span data-stu-id="5cb96-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="5cb96-110">完成作業之後，您可以執行 CsTopology Cmdlet 來啟用帳戶和 Lync Server 2013 網站之間的關聯。</span><span class="sxs-lookup"><span data-stu-id="5cb96-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="5cb96-111">在其他專案中，這會在 Active Directory 網域服務（AD DS）中建立必要的服務主體名稱（SPN）。</span><span class="sxs-lookup"><span data-stu-id="5cb96-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="5cb96-112">SPN 讓用戶端應用程式能夠找到特定的服務。</span><span class="sxs-lookup"><span data-stu-id="5cb96-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="5cb96-113">如需詳細資訊，請參閱作業檔中的[新 CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) 。</span><span class="sxs-lookup"><span data-stu-id="5cb96-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="5cb96-114">最佳做法</span><span class="sxs-lookup"><span data-stu-id="5cb96-114">Best Practices</span></span>

<span data-ttu-id="5cb96-115">為了協助提高 IIS 的安全性，建議您為 IIS 實施 Kerberos 帳戶。</span><span class="sxs-lookup"><span data-stu-id="5cb96-115">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS.</span></span> <span data-ttu-id="5cb96-116">如果您沒有實現 Kerberos 帳戶，IIS 會在標準使用者帳戶下執行。</span><span class="sxs-lookup"><span data-stu-id="5cb96-116">If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

