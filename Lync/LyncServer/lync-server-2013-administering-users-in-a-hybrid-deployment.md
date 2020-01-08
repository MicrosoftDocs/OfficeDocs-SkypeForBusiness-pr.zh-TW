---
title: Lync Server 2013：管理混合式部署中的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7804aacb226d06fbf239939658b6592d438a84f9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40974377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="3e945-102">在混合式 Lync Server 2013 部署中管理使用者</span><span class="sxs-lookup"><span data-stu-id="3e945-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e945-103">_**主題上次修改日期：** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="3e945-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="3e945-104">您可以使用 Microsoft Office 365 Online 入口網站中提供的使用者管理功能，來管理遷移至 Lync Online 之使用者的使用者設定和原則。</span><span class="sxs-lookup"><span data-stu-id="3e945-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="3e945-105">您必須使用您的租使用者系統管理員帳戶登入，才能執行系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="3e945-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="3e945-106">將使用者移回內部部署</span><span class="sxs-lookup"><span data-stu-id="3e945-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="3e945-107">本節僅適用于為 Lync 內部部署所建立和啟用的使用者，然後從內部部署部署移至 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="3e945-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="3e945-108">如果您想要移動在 Lync Online 中建立的使用者（在內部部署部署中不會啟用 Lync），請參閱在<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync Server 2013 中將使用者從 Lync Online 移至 lync 內部部署</A>。</span><span class="sxs-lookup"><span data-stu-id="3e945-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="3e945-109">執行下列 Cmdlet，將使用者從 Lync Online 移回 Lync 內部部署：</span><span class="sxs-lookup"><span data-stu-id="3e945-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="3e945-110">針對**HostedMigrationOverrideUrl**參數指定的 url 格式，必須是正在執行託管遷移服務之池的 url，格式如下：</span><span class="sxs-lookup"><span data-stu-id="3e945-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="3e945-111">Https://\<池 FQDN\>/HostedMigration/hostedmigrationService.svc。</span><span class="sxs-lookup"><span data-stu-id="3e945-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="3e945-112">您可以透過查看 Office 365 租使用者帳戶的 Lync Online 控制台 URL 來判斷託管遷移服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="3e945-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="3e945-113">**若要為您的 Office 365 租使用者判斷託管的遷移服務 URL**</span><span class="sxs-lookup"><span data-stu-id="3e945-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="3e945-114">以系統管理員身分登入您的 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="3e945-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="3e945-115">開啟**Lync 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="3e945-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="3e945-116">在**Lync 系統管理中心**顯示的狀態下，選取並將網址列中的 URL 複製到**lync.com**。</span><span class="sxs-lookup"><span data-stu-id="3e945-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="3e945-117">範例 URL 看起來類似以下所示：</span><span class="sxs-lookup"><span data-stu-id="3e945-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="3e945-118">將 URL 中的**webdir 為 admin**取代為系統**管理員**，並產生下列結果：</span><span class="sxs-lookup"><span data-stu-id="3e945-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="3e945-119">將下列字串附加到 URL： **/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="3e945-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="3e945-120">產生的 URL （即**HostedMigrationOverrideUrl**的值）應如下所示：</span><span class="sxs-lookup"><span data-stu-id="3e945-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

