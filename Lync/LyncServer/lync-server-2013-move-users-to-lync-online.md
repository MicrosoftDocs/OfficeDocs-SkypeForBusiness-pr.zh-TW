---
title: Lync Server 2013：將使用者移至 Lync Online
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
ms.openlocfilehash: 3dcc72c0f9934aebf28838cfd79899e1ce7aa2bc
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="beda8-102">在 Lync Server 2013 中將使用者移至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="beda8-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beda8-103">_**主題上次修改日期：** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="beda8-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="beda8-104">開始將使用者遷移至 Lync Online 之前，您應該備份與要移動之帳戶相關聯的使用者資料。</span><span class="sxs-lookup"><span data-stu-id="beda8-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="beda8-105">不是所有使用者資料都是以使用者帳戶移動。</span><span class="sxs-lookup"><span data-stu-id="beda8-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="beda8-106">如需詳細資訊，請參閱[Lync Server 2013： data 中的備份和還原需求](lync-server-2013-backup-and-restoration-requirements-data.md)。</span><span class="sxs-lookup"><span data-stu-id="beda8-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="beda8-107">將使用者設定遷移至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="beda8-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="beda8-108">使用者設定會與使用者帳戶一起移動。</span><span class="sxs-lookup"><span data-stu-id="beda8-108">User settings are moved with the user account.</span></span> <span data-ttu-id="beda8-109">有些內部部署設定不會與使用者帳戶一起移動。</span><span class="sxs-lookup"><span data-stu-id="beda8-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="beda8-110">將試驗使用者移至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="beda8-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="beda8-111">在您開始將使用者移至 Lync Online 之前，您可能會想要移動一些試驗使用者，以確認您的環境已正確設定。</span><span class="sxs-lookup"><span data-stu-id="beda8-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="beda8-112">然後，您可以在嘗試移動其他使用者之前，確認 Lync 功能及服務是否如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="beda8-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="beda8-113">若要將內部部署使用者移至 Lync Online 租使用者，請在 Lync Server 管理命令介面中，使用 Microsoft 365 或 Office 365 組織的系統管理員認證來執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="beda8-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="beda8-114">將 "username@contoso.com" 取代為您想要移動之使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="beda8-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="beda8-115">針對**HostedMigrationOverrideUrl**參數所指定的 url 格式，必須是正在執行裝載遷移服務之集區的 url，格式如下： Https:// \< 集區 FQDN \> /HostedMigration/hostedmigrationService.svc。</span><span class="sxs-lookup"><span data-stu-id="beda8-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="beda8-116">您可以透過查看 Microsoft 365 或 Office 365 組織帳戶的 Lync Online 控制台 URL，來決定主控遷移服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="beda8-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>

<span data-ttu-id="beda8-117">**決定組織的主控遷移服務 URL**</span><span class="sxs-lookup"><span data-stu-id="beda8-117">**To determine the Hosted Migration Service URL for your organization**</span></span>

1.  <span data-ttu-id="beda8-118">以系統管理員身分登入您的 Microsoft 365 或 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="beda8-118">Login to your Microsoft 365 or Office 365 organization as an administrator.</span></span>

2.  <span data-ttu-id="beda8-119">開啟**Lync 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="beda8-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="beda8-120">在 [ **Lync 系統管理中心**] 顯示時，選取 [位址] 列中的 URL，並將其複製到**lync.com**。</span><span class="sxs-lookup"><span data-stu-id="beda8-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="beda8-121">URL 的範例類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="beda8-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="beda8-122">使用系統**管理員**取代 URL 中的**webdir** ，產生下列結果：</span><span class="sxs-lookup"><span data-stu-id="beda8-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="beda8-123">在 URL: **/HostedMigration/hostedmigrationservice.svc**中附加下列字串。</span><span class="sxs-lookup"><span data-stu-id="beda8-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="beda8-124">產生的 URL （ **HostedMigrationOverrideUrl**的值）應如下所示：</span><span class="sxs-lookup"><span data-stu-id="beda8-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="beda8-125">將使用者移至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="beda8-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="beda8-126">您可以使用[Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Cmdlet 搭配– Filter 參數，選取具有指派給使用者帳戶之特定屬性的使用者，例如 RegistrarPool。</span><span class="sxs-lookup"><span data-stu-id="beda8-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="beda8-127">然後，您可以將傳回的使用者輸送至[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) Cmdlet，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="beda8-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="beda8-128">您也可以使用– OU 參數來取得指定 OU 中的所有使用者，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="beda8-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="beda8-129">驗證 Lync Online 使用者設定與功能</span><span class="sxs-lookup"><span data-stu-id="beda8-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="beda8-130">您可以透過下列方式確認使用者已成功移動：</span><span class="sxs-lookup"><span data-stu-id="beda8-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="beda8-131">在 [Lync Online 控制台] 中查看使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="beda8-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="beda8-132">內部部署使用者和線上使用者的視覺指示器是不同的。</span><span class="sxs-lookup"><span data-stu-id="beda8-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="beda8-133">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="beda8-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

