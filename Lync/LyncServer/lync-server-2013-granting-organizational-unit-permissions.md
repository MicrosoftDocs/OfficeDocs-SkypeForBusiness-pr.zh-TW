---
title: Lync Server 2013： 授與組織單位權限
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
ms.openlocfilehash: 85c43cb727b83b06d6427e2bf3b6027d78dc025e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="e1024-102">授與 Lync Server 2013 中的組織單位權限</span><span class="sxs-lookup"><span data-stu-id="e1024-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1024-103">_**主題上次修改日期：** 2012年-05-14_</span><span class="sxs-lookup"><span data-stu-id="e1024-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="e1024-104">您可以使用**Grant-csoupermission** cmdlet 授與權限指定組織單位 (Ou) 中的物件，使樹系準備所建立的 RTC 萬用群組的成員可以存取其不需要以 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e1024-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="e1024-105">新增至所指定 OU 的權限是相同的權限**Enable-csaddomain** cmdlet 新增至電腦和使用者在網域準備期間的容器。</span><span class="sxs-lookup"><span data-stu-id="e1024-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="e1024-106">使用**Test-csoupermission** cmdlet 來確認您使用**Grant-csoupermission** cmdlet 設定的權限。</span><span class="sxs-lookup"><span data-stu-id="e1024-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="e1024-107">您可以使用**Revoke-csoupermission** cmdlet 來移除您所使用**Grant-csoupermission** cmdlet 授與的權限。</span><span class="sxs-lookup"><span data-stu-id="e1024-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="e1024-108">若要授與 OU 權限</span><span class="sxs-lookup"><span data-stu-id="e1024-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="e1024-109">登入您要授與 OU 權限的網域中執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="e1024-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="e1024-110">如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e1024-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="e1024-111">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="e1024-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e1024-112">執行：</span><span class="sxs-lookup"><span data-stu-id="e1024-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e1024-113">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="e1024-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="e1024-114">若要驗證 OU 權限</span><span class="sxs-lookup"><span data-stu-id="e1024-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="e1024-115">登入您要驗證您使用**Grant-csoupermission** cmdlet 授與 OU 權限的網域中執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="e1024-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="e1024-116">如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e1024-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="e1024-117">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="e1024-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e1024-118">執行：</span><span class="sxs-lookup"><span data-stu-id="e1024-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e1024-119">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="e1024-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="e1024-120">若要撤銷 OU 權限</span><span class="sxs-lookup"><span data-stu-id="e1024-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="e1024-121">登入您要撤銷 OU 權限已由**Grant-csoupermission** cmdlet 授與網域中執行 Lync Server 2013 的電腦。</span><span class="sxs-lookup"><span data-stu-id="e1024-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="e1024-122">如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e1024-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="e1024-123">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="e1024-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e1024-124">執行：</span><span class="sxs-lookup"><span data-stu-id="e1024-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="e1024-125">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="e1024-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

