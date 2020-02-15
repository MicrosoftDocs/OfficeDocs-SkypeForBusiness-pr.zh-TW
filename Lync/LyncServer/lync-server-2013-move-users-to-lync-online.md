---
title: Lync Server 2013： 將使用者移至 Lync Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f39f28a2a642a30621e7fd3fd9d8a1beea9a4e14
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="d649a-102">將使用者移至 Lync Online 在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d649a-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d649a-103">_**上次修改主題：** 2014年-05-29_</span><span class="sxs-lookup"><span data-stu-id="d649a-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="d649a-104">在開始移轉至 Lync Online 使用者之前，您應該備份要移動的帳戶相關聯的使用者資料。</span><span class="sxs-lookup"><span data-stu-id="d649a-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="d649a-105">並非所有使用者資料都移動的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d649a-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="d649a-106">如需資訊，請參閱[Lync Server 2013 中的備份和還原需求： 資料](lync-server-2013-backup-and-restoration-requirements-data.md)。</span><span class="sxs-lookup"><span data-stu-id="d649a-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="d649a-107">將使用者設定移轉至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="d649a-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="d649a-108">使用者設定都會移與使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d649a-108">User settings are moved with the user account.</span></span> <span data-ttu-id="d649a-109">內部部署的某些設定不會移動與使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d649a-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="d649a-110">將試驗使用者移至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="d649a-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="d649a-111">開始將使用者移至 Lync Online 之前，您可能要移動一些試驗使用者，以確認已正確設定您的環境。</span><span class="sxs-lookup"><span data-stu-id="d649a-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="d649a-112">然後，您可以驗證該 Lync 功能和服務函式預期，再嘗試移動其他使用者。</span><span class="sxs-lookup"><span data-stu-id="d649a-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="d649a-113">若要將內部部署使用者移至 Lync Online 租用戶，執行下列 cmdlet 以 Lync Server 管理命令介面，使用您的 Microsoft Office 365 租用戶的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="d649a-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="d649a-114">「 Username@contoso.com 」 取代為您想要移動使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="d649a-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="d649a-115">格式如**HostedMigrationOverrideUrl**參數必須是主控遷移服務執行，以下列格式的集區的 URL 所指定的 URL: Https://\<集區 FQDN\>/HostedMigration/hostedmigrationService.svc。</span><span class="sxs-lookup"><span data-stu-id="d649a-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="d649a-116">您可以透過檢視 URL 的 Office 365 租用戶帳戶的 Lync Online 控制台判斷主控移轉服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="d649a-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="d649a-117">**若要判斷您 Office 365 租用戶主控移轉服務 URL**</span><span class="sxs-lookup"><span data-stu-id="d649a-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="d649a-118">Office 365 租用戶系統管理員身分登入。</span><span class="sxs-lookup"><span data-stu-id="d649a-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="d649a-119">開啟**Lync 系統管理中心**]。</span><span class="sxs-lookup"><span data-stu-id="d649a-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="d649a-120">顯示在**Lync 系統管理中心**，選取與複製最**lync.com**[網址] 列中的 URL。</span><span class="sxs-lookup"><span data-stu-id="d649a-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="d649a-121">範例 URL 看起來如下：</span><span class="sxs-lookup"><span data-stu-id="d649a-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="d649a-122">**Webdir** URL 中取代為**系統管理員**，結果如下：</span><span class="sxs-lookup"><span data-stu-id="d649a-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="d649a-123">將下列字串附加至的 URL: **/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="d649a-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="d649a-124">產生的 URL，也就是**HostedMigrationOverrideUrl**的值，應該如下所示：</span><span class="sxs-lookup"><span data-stu-id="d649a-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="d649a-125">將使用者移至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="d649a-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="d649a-126">您可以移動多位使用者使用[Get-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 搭配 – Filter 參數來選取的使用者使用指派給使用者帳戶，例如 RegistrarPool 特定屬性。</span><span class="sxs-lookup"><span data-stu-id="d649a-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="d649a-127">您可以再透過管線傳[Move-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet 時，傳回的使用者在下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="d649a-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="d649a-128">您也可以使用 – OU 參數來擷取所有使用者在指定之 OU 中，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="d649a-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="d649a-129">確認 Lync Online 使用者設定及功能</span><span class="sxs-lookup"><span data-stu-id="d649a-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="d649a-130">您可以確認使用者已成功移動方式如下：</span><span class="sxs-lookup"><span data-stu-id="d649a-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="d649a-131">在 Lync Online Control Panel 中檢視使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="d649a-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="d649a-132">內部部署使用者和 online 使用者視覺標記為不同。</span><span class="sxs-lookup"><span data-stu-id="d649a-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="d649a-133">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d649a-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

