---
title: 移轉通話駐留應用程式設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba55ec7ff54858d3324df2ab8794176a5dc7a10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="aa814-102">移轉通話駐留應用程式設定</span><span class="sxs-lookup"><span data-stu-id="aa814-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa814-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="aa814-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="aa814-104">從 Lync Server 2010 將呼叫駐留應用程式遷移至 Lync Server 2013，包括設定 Lync Server 2013 池以及在 Lync Server 2010 中上傳的任何自訂音樂保留檔案，還原服務層級設定和 retargeting所有呼叫公園軌道式移至 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="aa814-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="aa814-105">如果您已在 Lync Server 2010 pool 中設定自訂的音樂保留檔案，則需要將這些檔案複製到新的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="aa814-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="aa814-106">此外，建議您將來自 Lync Server 2010 的任何通話駐留自訂的音樂保留檔案從 Lync Server 備份到另一個目的地，以保留針對通話駐留上傳的任何自訂音樂保留檔案的個別備份複本。</span><span class="sxs-lookup"><span data-stu-id="aa814-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="aa814-107">通話駐留應用程式的自訂音樂保留檔案會儲存在該池的檔案存放區中。</span><span class="sxs-lookup"><span data-stu-id="aa814-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="aa814-108">若要將 Lync Server 2010 pool 檔案存放區中的音訊檔案複製到 Lync Server 2013 檔案存放區，請使用**Xcopy**命令及下列參數：</span><span class="sxs-lookup"><span data-stu-id="aa814-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="aa814-109">當所有自訂的音訊檔案都已複製到 Lync Server 2013 檔案存放區時，必須設定 Lync Server 2013 池的通話駐留應用程式設定，而且與 Lync Server 2010 pool 相關聯的通話駐留軌道的範圍必須重新指派給Lync Server 2013 pool。</span><span class="sxs-lookup"><span data-stu-id="aa814-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="aa814-110">[通話駐留] 應用程式設定包括拾取超時閾值、啟用或停用音樂、最大的呼叫挑選嘗試與超時要求。</span><span class="sxs-lookup"><span data-stu-id="aa814-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="aa814-111">您必須使用 Lync Server 管理命令介面來執行**CsCpsConfiguration** Cmdlet，以管理通話駐留應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="aa814-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="aa814-112">您無法使用 Lync Server [控制台] 管理 [通話駐留應用程式設定]。</span><span class="sxs-lookup"><span data-stu-id="aa814-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="aa814-113">**重新設定通話公園服務設定**</span><span class="sxs-lookup"><span data-stu-id="aa814-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="aa814-114">從 Lync Server 2013 前端伺服器，開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="aa814-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="aa814-115">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="aa814-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa814-116">如果您的 Lync Server 2013 通話駐留應用程式設定與舊版 Lync Server 2010 設定相同，您可以略過執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="aa814-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="aa814-117">如果 Lync Server 2013 和 Lync Server 2010 環境的通話駐留應用程式設定不同，請使用以下 Cmdlet 做為範本來更新這些變更。</span><span class="sxs-lookup"><span data-stu-id="aa814-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

<span data-ttu-id="aa814-118">若要將所有通話駐留軌道範圍從 Lync Server 2010 pool 重新指派給 Lync Server 2013，您可以使用 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="aa814-118">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="aa814-119">**使用 Lync Server [控制台] 重新分派所有通話駐留軌道的範圍**</span><span class="sxs-lookup"><span data-stu-id="aa814-119">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="aa814-120">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="aa814-120">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="aa814-121">在左窗格中，選取 [**語音功能**]。</span><span class="sxs-lookup"><span data-stu-id="aa814-121">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="aa814-122">選取 [**通話駐留**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="aa814-122">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="aa814-123">針對指派給 Lync Server 2010 pool 的每個通話駐留軌道範圍，請編輯**目的地伺服器**設定的 FQDN，然後選取將處理通話寄存要求的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="aa814-123">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="aa814-124">選取 [**確認**]，儲存變更。</span><span class="sxs-lookup"><span data-stu-id="aa814-124">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="aa814-125">**使用 Lync Server 管理命令介面重新分派所有通話駐留軌道的範圍**</span><span class="sxs-lookup"><span data-stu-id="aa814-125">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="aa814-126">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="aa814-126">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="aa814-127">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="aa814-127">At the command line, type the following:</span></span>
    
        Get-CsCallParkOrbit
    
    <span data-ttu-id="aa814-128">這個 Cmdlet 會列出部署中所有的通話駐留軌道的範圍。</span><span class="sxs-lookup"><span data-stu-id="aa814-128">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="aa814-129">所有已設定為 Lync Server 2010 池之**CallParkServiceId**和**CallParkServerFqdn**參數的通話駐留軌道式，都必須重新分派。</span><span class="sxs-lookup"><span data-stu-id="aa814-129">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="aa814-130">若要將 Lync Server 2010 通話駐留軌道範圍重新指派給 Lync Server 2013 池，請在命令列輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="aa814-130">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

<span data-ttu-id="aa814-131">將所有通話駐留軌道範圍重新指派給 Lync Server 2013 池之後，通話駐留應用程式的遷移程式將會完成，而 Lync Server 2013 池會處理所有未來的通話駐留要求。</span><span class="sxs-lookup"><span data-stu-id="aa814-131">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

