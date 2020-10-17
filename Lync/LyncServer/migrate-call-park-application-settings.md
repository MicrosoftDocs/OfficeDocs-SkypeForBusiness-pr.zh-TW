---
title: 移轉通話駐留應用程式設定
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63b91c6a742310d14031bdadc28cbc6ca57e115
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503560"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="7ffec-102">移轉通話駐留應用程式設定</span><span class="sxs-lookup"><span data-stu-id="7ffec-102">Migrate Call Park application settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ffec-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7ffec-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7ffec-104">從 Lync Server 2010 到 Lync Server 2013 的通話駐留應用程式的遷移包括布建 Lync Server 2013 集區，其中包含已在 Lync Server 2010 中上傳的任何自訂音樂保留檔案，還原服務層級設定，並 retargeting 所有通話駐留軌道至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="7ffec-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="7ffec-105">如果已在 Lync Server 2010 集區中設定自訂的已等候音樂檔案，則需要將這些檔案複製到新的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="7ffec-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="7ffec-106">此外，建議您將所有通話駐留自訂的封存檔案從 Lync Server 2010 備份到另一個目的地，以保留針對通話保留所上傳之任何自訂待等候音樂檔案的個別備份副本。</span><span class="sxs-lookup"><span data-stu-id="7ffec-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="7ffec-107">通話駐留應用程式的自訂等候音樂檔案會儲存在集區的檔案存放區中。</span><span class="sxs-lookup"><span data-stu-id="7ffec-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="7ffec-108">若要將 Lync Server 2010 集區檔案存放區的音訊檔複製到 Lync Server 2013 檔存放區，請使用具有下列參數的 **Xcopy** 命令：</span><span class="sxs-lookup"><span data-stu-id="7ffec-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="7ffec-109">當所有自訂音訊檔案都複製到 Lync Server 2013 檔案存放區時，必須設定 Lync Server 2013 集區的通話駐留應用程式設定，而且與 Lync Server 2010 集區相關聯的通話駐留軌道範圍必須重新指派至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="7ffec-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="7ffec-110">通話駐留應用程式設定包括收取的超時閾值、啟用或停用等候的音樂、呼叫收取的最大嘗試及超時要求。</span><span class="sxs-lookup"><span data-stu-id="7ffec-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="7ffec-111">您必須使用 Lync Server 管理命令介面來管理通話駐留應用程式設定，以執行 **Set-CsCpsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7ffec-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="7ffec-112">您無法使用 Lync Server 控制台管理通話駐留應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="7ffec-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="7ffec-113">**重新設定通話駐留應用程式設定**</span><span class="sxs-lookup"><span data-stu-id="7ffec-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="7ffec-114">在 Lync Server 2013 前端伺服器上，開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="7ffec-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="7ffec-115">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7ffec-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ffec-116">如果您的 Lync Server 2013 通話駐留應用程式設定與舊版 Lync Server 2010 設定相同，您可以略過執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="7ffec-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="7ffec-117">如果 Lync Server 2013 和 Lync Server 2010 環境的通話駐留應用程式設定不同，請使用下列 Cmdlet 做為範本以更新這些變更。</span><span class="sxs-lookup"><span data-stu-id="7ffec-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="7ffec-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" <LS2010 CPS value> "-MaxCallPickupAttempts" " <LS2010 CPS pickup attempts> -OnTimeoutURI" <LS2010 CPS timeout URI> " ```</span><span class="sxs-lookup"><span data-stu-id="7ffec-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="7ffec-119">若要將所有通話駐留軌道範圍從 Lync Server 2010 集區重新指派至 Lync Server 2013 集區，您可以使用 Lync Server 控制台或 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="7ffec-119">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="7ffec-120">**使用 Lync Server 控制台重新指派所有通話駐留軌道範圍**</span><span class="sxs-lookup"><span data-stu-id="7ffec-120">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="7ffec-121">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="7ffec-121">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="7ffec-122">在左窗格中，選取 [語音功能]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ffec-122">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="7ffec-123">選取 [通話駐留]\*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7ffec-123">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="7ffec-124">針對指派給 Lync Server 2010 集區的每個通話駐留軌道範圍，編輯 [ **目的地伺服器的 FQDN** ] 設定，並選取要處理通話駐留要求的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="7ffec-124">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="7ffec-125">選取 [認可]\*\*\*\* 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="7ffec-125">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="7ffec-126">**使用 Lync Server 管理命令介面重新指派所有通話駐留軌道範圍**</span><span class="sxs-lookup"><span data-stu-id="7ffec-126">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="7ffec-127">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="7ffec-127">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="7ffec-128">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7ffec-128">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="7ffec-129">此 Cmdlet 會列出部署中的所有通話駐留軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="7ffec-129">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="7ffec-130">所有已設定為 Lync Server 2010 集區之 **CallParkServiceId** 和 **CallParkServerFqdn** 參數的通話駐留軌道都必須重新指派。</span><span class="sxs-lookup"><span data-stu-id="7ffec-130">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="7ffec-131">若要將 Lync Server 2010 通話駐留軌道範圍重新指派至 Lync Server 2013 集區，請在命令列中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7ffec-131">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="7ffec-132">將所有通話駐留軌道範圍重新指派至 Lync Server 2013 集區之後，通話駐留應用程式的遷移程式就會完成，Lync Server 2013 集區將會處理所有未來的通話駐留要求。</span><span class="sxs-lookup"><span data-stu-id="7ffec-132">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

