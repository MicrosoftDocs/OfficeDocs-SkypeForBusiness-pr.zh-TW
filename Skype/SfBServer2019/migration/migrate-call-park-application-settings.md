---
title: 移轉通話駐留應用程式設定
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 通話駐留應用程式的遷移包含為商務用 Skype Server 2019 集區提供已在舊版安裝中上傳的任何自訂音樂保留檔案，還原服務等級設定，並將所有通話駐留軌道 retargeting 至商務用 Skype Server 2019 集區。 如果已在集區中設定自訂的已等候音樂檔案，則需要將這些檔案複製到新的商務用 Skype Server 2019 集區。 此外，建議您將所有通話駐留自訂的待進行音樂檔案，備份至另一個目的地，以保留針對通話保留所上傳之任何自訂待等候音樂檔案的個別備份副本。 通話駐留應用程式的自訂等候音樂檔案會儲存在集區的檔案存放區中。 若要將音訊檔從集區檔案存放區複製到商務用 Skype Server 2019 檔案存放區，請使用具有下列參數的 Xcopy 命令：
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752815"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="a62ef-107">移轉通話駐留應用程式設定</span><span class="sxs-lookup"><span data-stu-id="a62ef-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="a62ef-108">通話駐留應用程式的遷移包括布建商務用 Skype Server 2019 集區，其中包含已在舊版安裝中上傳的任何自訂音樂檔案，還原服務層級設定，並將所有通話駐留軌道重新設定為商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="a62ef-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a62ef-109">如果已在集區中設定自訂的已等候音樂檔案，則需要將這些檔案複製到新的商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="a62ef-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a62ef-110">此外，建議您將所有通話駐留自訂的待進行封存檔案備份到另一個目的地，以保留針對通話駐留上傳之任何自訂待等候音樂檔案的個別備份副本。</span><span class="sxs-lookup"><span data-stu-id="a62ef-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="a62ef-111">通話駐留應用程式的自訂等候音樂檔案會儲存在集區的檔案存放區中。</span><span class="sxs-lookup"><span data-stu-id="a62ef-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="a62ef-112">若要將音訊檔從集區檔案存放區複製到商務用 Skype Server 2019 檔案存放區，請使用具有下列參數的**Xcopy**命令：</span><span class="sxs-lookup"><span data-stu-id="a62ef-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="a62ef-113">當所有自訂音訊檔案都已複製到商務用 Skype server 2019 檔案存放區時，必須設定商務用 Skype Server 2019 集區的通話駐留應用程式設定，而且與舊版集區相關聯的通話駐留軌道範圍必須重新指派至商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="a62ef-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="a62ef-114">通話駐留應用程式設定包括收取的超時閾值、啟用或停用等候的音樂、呼叫收取的最大嘗試，以及超時要求。</span><span class="sxs-lookup"><span data-stu-id="a62ef-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="a62ef-115">您必須使用商務用 Skype Server 管理命令介面來管理通話駐留應用程式設定，以執行**Set-CsCpsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a62ef-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="a62ef-116">您無法使用商務用 Skype Server 控制台來管理通話駐留應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="a62ef-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="a62ef-117">重新設定通話駐留應用程式設定</span><span class="sxs-lookup"><span data-stu-id="a62ef-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="a62ef-118">從商務用 Skype Server 2019 前端伺服器，開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="a62ef-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="a62ef-119">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="a62ef-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="a62ef-120">如果商務用 Skype Server 2019 通話駐留應用程式設定與舊版設定相同，您可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="a62ef-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="a62ef-121">如果商務用 Skype Server 2019 和舊版環境中的通話駐留應用程式設定不同，請使用下列 Cmdlet 做為範本以更新這些變更。</span><span class="sxs-lookup"><span data-stu-id="a62ef-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="a62ef-122">若要將所有通話駐留軌道範圍從舊版集區重新指派至商務用 Skype Server 2019 集區，您可以使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="a62ef-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a62ef-123">使用商務用 Skype Server 控制台重新指派所有通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="a62ef-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a62ef-124">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a62ef-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a62ef-125">在左窗格中，選取 [語音功能]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a62ef-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="a62ef-126">選取 [通話駐留]\*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a62ef-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="a62ef-127">針對指派給舊版集區的每個通話駐留軌道範圍，編輯 [**目的地伺服器的 FQDN** ] 設定，並選取將處理通話駐留要求的商務用 Skype server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="a62ef-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="a62ef-128">選取 [認可]\*\*\*\* 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="a62ef-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a62ef-129">使用商務用 Skype Server 管理命令介面重新指派所有通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="a62ef-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a62ef-130">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="a62ef-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="a62ef-131">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="a62ef-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="a62ef-132">此 Cmdlet 會列出部署中的所有通話駐留軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="a62ef-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="a62ef-133">所有已設定為舊版集區之**CallParkServiceId**和**CallParkServerFqdn**參數的通話駐留軌道都必須重新指派。</span><span class="sxs-lookup"><span data-stu-id="a62ef-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="a62ef-134">若要將舊版通話駐留軌道範圍重新指派至商務用 Skype Server 2019 集區，請在命令列中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="a62ef-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="a62ef-135">將所有通話駐留軌道範圍重新指派至商務用 Skype Server 2019 集區之後，通話駐留應用程式的遷移程式就會完成，商務用 Skype Server 2019 集區將會處理所有未來的通話駐留要求。</span><span class="sxs-lookup"><span data-stu-id="a62ef-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


