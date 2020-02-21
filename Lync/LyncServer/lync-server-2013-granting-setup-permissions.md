---
title: Lync Server 2013： 授與安裝程式權限
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
ms.openlocfilehash: 647590131702addb8363b42aaa7d49e299b63a47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="fb490-102">授與 Lync Server 2013 中的設定權限</span><span class="sxs-lookup"><span data-stu-id="fb490-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb490-103">_**主題上次修改日期：** 2012 年 08 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="fb490-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="fb490-104">您可使用 **Grant-CsSetupPermission** Cmdlet，新增 Read、Write、ReadSPN 和 WriteSPN 權限給特定 Active Directory 組織單位 (OU) 的 RTCUniversalServerAdmins 群組。</span><span class="sxs-lookup"><span data-stu-id="fb490-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="fb490-105">然後 OU 可以安裝在指定的網域中執行 Lync Server 2013，不需要以 Domain Admins 群組的成員伺服器中使用 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fb490-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="fb490-106">使用 **Test-CsSetupPermission** Cmdlet，可以驗證您以 **Grant-CsSetupPermission** Cmdlet 設定的權限。</span><span class="sxs-lookup"><span data-stu-id="fb490-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="fb490-107">您可使用 **Revoke-CsSetupPermission** Cmdlet，移除您以 **Grant-CsSetupPermission** Cmdlet 授與的權限。</span><span class="sxs-lookup"><span data-stu-id="fb490-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="fb490-108">授與安裝程式權限</span><span class="sxs-lookup"><span data-stu-id="fb490-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="fb490-109">登入您要設定權限授與網域中執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="fb490-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="fb490-110">如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。</span><span class="sxs-lookup"><span data-stu-id="fb490-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="fb490-111">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="fb490-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fb490-112">執行：</span><span class="sxs-lookup"><span data-stu-id="fb490-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="fb490-p103">您可將 ComputerOu 參數指定為相對於指定網域的預設命名內容 (例如 CN=computers)。或者，也可以將此參數指定為完整的 OU 辨別名稱 (DN) (例如 "CN=computers,DC=Contoso,DC=com")。若為後者，您指定的 OU DN 必須與所指定網域維持一致。</span><span class="sxs-lookup"><span data-stu-id="fb490-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="fb490-116">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="fb490-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="fb490-117">確認安裝程式權限</span><span class="sxs-lookup"><span data-stu-id="fb490-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="fb490-118">登入您要驗證您使用**Grant-cssetuppermission** cmdlet 授與的安裝程式權限的網域中執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="fb490-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="fb490-119">如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。</span><span class="sxs-lookup"><span data-stu-id="fb490-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="fb490-120">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="fb490-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fb490-121">執行：</span><span class="sxs-lookup"><span data-stu-id="fb490-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="fb490-p105">您可將 ComputerOu 參數指定為相對於指定網域的預設命名內容 (例如 CN=computers)。或者，也可以將此參數指定為完整的 OU 辨別名稱 (DN) (例如 "CN=computers,DC=Contoso,DC=com")。若為後者，您指定的 OU DN 必須與所指定網域維持一致。</span><span class="sxs-lookup"><span data-stu-id="fb490-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="fb490-125">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="fb490-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="fb490-126">撤銷安裝程式權限</span><span class="sxs-lookup"><span data-stu-id="fb490-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="fb490-127">登入您要撤銷已授與**Grant-cssetuppermission** cmdlet 的安裝程式權限的網域中執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="fb490-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="fb490-128">如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。</span><span class="sxs-lookup"><span data-stu-id="fb490-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="fb490-129">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="fb490-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fb490-130">執行：</span><span class="sxs-lookup"><span data-stu-id="fb490-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="fb490-p107">您可將 ComputerOu 參數指定為相對於指定網域的預設命名內容 (例如 CN=computers)。或者，也可以將此參數指定為完整的 OU 辨別名稱 (DN) (例如 "CN=computers,DC=Contoso,DC=com")。若為後者，您指定的 OU DN 必須與所指定網域維持一致。</span><span class="sxs-lookup"><span data-stu-id="fb490-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="fb490-134">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="fb490-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

