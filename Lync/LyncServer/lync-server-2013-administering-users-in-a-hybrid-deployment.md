---
title: Lync Server 2013： 管理混合部署中的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03819bdf387c426c3a0bda5074ad0a36021f68c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="cf9ff-102">管理混合 Lync Server 2013 部署中的使用者</span><span class="sxs-lookup"><span data-stu-id="cf9ff-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf9ff-103">_**上次修改主題：** 2014年-05-29_</span><span class="sxs-lookup"><span data-stu-id="cf9ff-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="cf9ff-104">您可以管理使用者設定和原則的使用者移轉至 Lync Online 使用 Microsoft Office 365 線上入口網站中可用的使用者管理功能。</span><span class="sxs-lookup"><span data-stu-id="cf9ff-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="cf9ff-105">使用您的租用戶系統管理員帳戶來執行管理工作，您必須登入。</span><span class="sxs-lookup"><span data-stu-id="cf9ff-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="cf9ff-106">將使用者移回內部部署</span><span class="sxs-lookup"><span data-stu-id="cf9ff-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="cf9ff-107">本節僅適用於已建立並啟用 Lync 內部部署，然後移至 Lync Online 的 [從內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="cf9ff-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="cf9ff-108">如果您想要移動的使用者，已建立在 Lync Online （並不屬於啟用 lync 內部部署中），請參閱<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">移動使用者從 Lync Online lync 內部部署 Lync Server 2013 中</A>。</span><span class="sxs-lookup"><span data-stu-id="cf9ff-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="cf9ff-109">執行下列 cmdlet，將使用者移從 Lync Online 回至 Lync 內部部署：</span><span class="sxs-lookup"><span data-stu-id="cf9ff-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="cf9ff-110">**HostedMigrationOverrideUrl**參數所指定的 URL 的格式必須是主控遷移服務執行，以下列格式的集區的 URL:</span><span class="sxs-lookup"><span data-stu-id="cf9ff-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="cf9ff-111">Https://\<集區 FQDN\>/HostedMigration/hostedmigrationService.svc。</span><span class="sxs-lookup"><span data-stu-id="cf9ff-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="cf9ff-112">您可以透過檢視 URL 的 Office 365 租用戶帳戶的 Lync Online 控制台判斷主控移轉服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="cf9ff-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="cf9ff-113">**若要判斷您 Office 365 租用戶主控移轉服務 URL**</span><span class="sxs-lookup"><span data-stu-id="cf9ff-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="cf9ff-114">Office 365 租用戶系統管理員身分登入。</span><span class="sxs-lookup"><span data-stu-id="cf9ff-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="cf9ff-115">開啟**Lync 系統管理中心**]。</span><span class="sxs-lookup"><span data-stu-id="cf9ff-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="cf9ff-116">顯示在**Lync 系統管理中心**，選取與複製最**lync.com**[網址] 列中的 URL。</span><span class="sxs-lookup"><span data-stu-id="cf9ff-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="cf9ff-117">範例 URL 看起來如下：</span><span class="sxs-lookup"><span data-stu-id="cf9ff-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="cf9ff-118">**Webdir** URL 中取代為**系統管理員**，結果如下：</span><span class="sxs-lookup"><span data-stu-id="cf9ff-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="cf9ff-119">將下列字串附加至的 URL: **/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="cf9ff-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="cf9ff-120">產生的 URL，也就是**HostedMigrationOverrideUrl**的值，應該如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf9ff-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

