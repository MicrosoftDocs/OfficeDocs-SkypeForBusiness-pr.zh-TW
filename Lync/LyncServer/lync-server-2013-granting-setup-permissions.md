---
title: Lync Server 2013：授與設定權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="17dfc-102">在 Lync Server 2013 中授與設定權限</span><span class="sxs-lookup"><span data-stu-id="17dfc-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17dfc-103">_**主題上次修改日期：** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="17dfc-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="17dfc-104">您可以使用**Grant CsSetupPermission** Cmdlet，在指定的 Active Directory 組織單位（OU）中，為 RTCUniversalServerAdmins 群組新增讀取、寫入、ReadSPN 和 WriteSPN 許可權。</span><span class="sxs-lookup"><span data-stu-id="17dfc-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="17dfc-105">然後，該 OU 中 [RTCUniversalServerAdmins] 群組的成員可以安裝執行 Lync Server 2013 的伺服器，而不是 [網域管理員] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="17dfc-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="17dfc-106">使用**CsSetupPermission** Cmdlet 來驗證您使用**Grant CsSetupPermission** Cmdlet 設定的許可權。</span><span class="sxs-lookup"><span data-stu-id="17dfc-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="17dfc-107">您可以使用**Revoke CsSetupPermission** Cmdlet 來移除您使用**Grant CsSetupPermission** Cmdlet 所授予的許可權。</span><span class="sxs-lookup"><span data-stu-id="17dfc-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="17dfc-108">若要授與設定許可權</span><span class="sxs-lookup"><span data-stu-id="17dfc-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="17dfc-109">在您想要授與設定許可權的網域中，登入執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="17dfc-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="17dfc-110">如果組織單位位於不同的子域中，請使用屬於網域管理員群組或企業系統管理員群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="17dfc-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="17dfc-111">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="17dfc-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="17dfc-112">用盡</span><span class="sxs-lookup"><span data-stu-id="17dfc-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="17dfc-113">您可以指定 ComputerOu 參數，以相對於指定網域的預設命名內容（例如，CN = 電腦）。</span><span class="sxs-lookup"><span data-stu-id="17dfc-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="17dfc-114">或者，您也可以將此參數指定為完整的 OU 可分辨名稱（DN）（例如，「CN = 電腦，DC = Contoso，DC = com」）。</span><span class="sxs-lookup"><span data-stu-id="17dfc-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="17dfc-115">在後一個案例中，您必須指定與您指定之網域一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="17dfc-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="17dfc-116">如果您沒有指定 Domain 參數，則預設值為本地域。</span><span class="sxs-lookup"><span data-stu-id="17dfc-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="17dfc-117">驗證設定許可權</span><span class="sxs-lookup"><span data-stu-id="17dfc-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="17dfc-118">在您想要驗證您使用**Grant CsSetupPermission** Cmdlet 所授出的安裝許可權之網域中，登入運行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="17dfc-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="17dfc-119">如果組織單位位於不同的子域中，請使用屬於網域管理員群組或企業系統管理員群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="17dfc-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="17dfc-120">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="17dfc-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="17dfc-121">用盡</span><span class="sxs-lookup"><span data-stu-id="17dfc-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="17dfc-122">您可以指定 ComputerOu 參數，以相對於指定網域的預設命名內容（例如，CN = 電腦）。</span><span class="sxs-lookup"><span data-stu-id="17dfc-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="17dfc-123">或者，您也可以將此參數指定為完整的 OU 可分辨名稱（DN）（例如，「CN = 電腦，DC = Contoso，DC = com」）。</span><span class="sxs-lookup"><span data-stu-id="17dfc-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="17dfc-124">在後一個案例中，您必須指定與您指定之網域一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="17dfc-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="17dfc-125">如果您沒有指定 Domain 參數，則預設值為本地域。</span><span class="sxs-lookup"><span data-stu-id="17dfc-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="17dfc-126">撤銷設定許可權</span><span class="sxs-lookup"><span data-stu-id="17dfc-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="17dfc-127">在您想要吊銷**Grant CsSetupPermission** Cmdlet 所授的設定許可權的網域中，登入執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="17dfc-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="17dfc-128">如果組織單位位於不同的子域中，請使用屬於網域管理員群組或企業系統管理員群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="17dfc-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="17dfc-129">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="17dfc-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="17dfc-130">用盡</span><span class="sxs-lookup"><span data-stu-id="17dfc-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="17dfc-131">您可以指定 ComputerOu 參數，以相對於指定網域的預設命名內容（例如，CN = 電腦）。</span><span class="sxs-lookup"><span data-stu-id="17dfc-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="17dfc-132">或者，您也可以將此參數指定為完整的 OU 可分辨名稱（DN）（例如，「CN = 電腦，DC = Contoso，DC = com」）。</span><span class="sxs-lookup"><span data-stu-id="17dfc-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="17dfc-133">在後一個案例中，您必須指定與您指定之網域一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="17dfc-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="17dfc-134">如果您沒有指定 Domain 參數，則預設值為本地域。</span><span class="sxs-lookup"><span data-stu-id="17dfc-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

