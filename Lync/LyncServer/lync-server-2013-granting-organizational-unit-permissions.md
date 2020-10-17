---
title: Lync Server 2013：授與組織單位許可權
description: Lync Server 2013：授與組織單位許可權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ad862241e409190620afa7dbf4fa73adf339de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554509"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="1fe16-103">在 Lync Server 2013 中授與組織單位許可權</span><span class="sxs-lookup"><span data-stu-id="1fe16-103">Granting organizational unit permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fe16-104">_**主題上次修改日期：** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="1fe16-104">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="1fe16-105">您可以使用 **Grant-CsOuPermission** 指令程式將許可權授與指定組織單位中的物件 (ou) ，使樹系準備建立的 RTC 通用群組成員可以存取，而不是 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1fe16-105">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="1fe16-106">新增至指定 OU 的許可權與 **Enable-CsAdDomain** Cmdlet 會在網域準備期間新增至電腦和使用者容器的許可權相同。</span><span class="sxs-lookup"><span data-stu-id="1fe16-106">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="1fe16-107">使用 **Test-CsOuPermission** Cmdlet 來驗證您使用 **Grant-CsOuPermission** Cmdlet 所設定的許可權。</span><span class="sxs-lookup"><span data-stu-id="1fe16-107">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="1fe16-108">您可以使用 **Revoke-CsOuPermission** Cmdlet 來移除使用 **Grant-CsOuPermission** Cmdlet 所授與的許可權。</span><span class="sxs-lookup"><span data-stu-id="1fe16-108">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="1fe16-109">授與 OU 許可權</span><span class="sxs-lookup"><span data-stu-id="1fe16-109">To grant OU permissions</span></span>

1.  <span data-ttu-id="1fe16-110">在您想要授與 OU 許可權的網域中登入執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="1fe16-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="1fe16-111">如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1fe16-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="1fe16-112">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1fe16-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1fe16-113">運行：</span><span class="sxs-lookup"><span data-stu-id="1fe16-113">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="1fe16-114">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="1fe16-114">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="1fe16-115">驗證 OU 許可權</span><span class="sxs-lookup"><span data-stu-id="1fe16-115">To verify OU permissions</span></span>

1.  <span data-ttu-id="1fe16-116">在您想要驗證您使用 **Grant-CsOuPermission** Cmdlet 所授與之 OU 許可權的網域中登入執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="1fe16-116">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="1fe16-117">如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1fe16-117">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="1fe16-118">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1fe16-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1fe16-119">運行：</span><span class="sxs-lookup"><span data-stu-id="1fe16-119">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="1fe16-120">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="1fe16-120">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="1fe16-121">撤銷 OU 許可權</span><span class="sxs-lookup"><span data-stu-id="1fe16-121">To revoke OU permissions</span></span>

1.  <span data-ttu-id="1fe16-122">在您要撤銷 **Grant-CsOuPermission** Cmdlet 所授與之 OU 許可權的網域中，登入執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="1fe16-122">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="1fe16-123">如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1fe16-123">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="1fe16-124">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1fe16-124">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1fe16-125">運行：</span><span class="sxs-lookup"><span data-stu-id="1fe16-125">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="1fe16-126">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="1fe16-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

