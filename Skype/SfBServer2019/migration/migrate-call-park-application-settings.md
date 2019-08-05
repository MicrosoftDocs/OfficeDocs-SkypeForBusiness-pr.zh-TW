---
title: 遷移通話駐留應用程式設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '[通話駐留] 應用程式的遷移包括設定商務用 Skype Server 2019 池, 其中包含已在舊版安裝中上傳的任何自訂音樂保留檔案, 還原服務層級設定並 retargeting 所有通話駐留軌道式商務用 Skype Server 2019 池。 如果已在池中設定自訂的 [封存暫停] 檔案, 則需要將這些檔案複製到新的商務用 Skype Server 2019 池。 此外, 建議您將任何通話駐留自訂的音樂保留檔案從另一個目的地備份, 以保留針對通話駐留上傳的任何自訂音樂保留檔案的個別備份複本。 通話駐留應用程式的自訂音樂保留檔案會儲存在該池的檔案存放區中。 若要將文件庫檔案存放區中的音訊檔案複製到商務用 Skype Server 2019 檔案存放區, 請使用 Xcopy 命令及下列參數:'
ms.openlocfilehash: aa4ac3cfbe6802b8853a8ec8886f8fffe1a20a51
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189082"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="b8d9b-107">遷移通話駐留應用程式設定</span><span class="sxs-lookup"><span data-stu-id="b8d9b-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="b8d9b-108">[通話駐留] 應用程式的遷移包括設定商務用 Skype Server 2019 池, 其中包含已在舊版安裝中上傳的任何自訂音樂保留檔案, 還原服務層級設定並重新導向所有通話駐留軌道式[商務用 Skype Server 2019] 池。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b8d9b-109">如果已在池中設定自訂的 [封存暫停] 檔案, 則需要將這些檔案複製到新的商務用 Skype Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b8d9b-110">此外, 建議您將任何通話駐留自訂的 [封存] 檔案移到另一個目的地, 以保留針對通話駐留上傳的任何自訂音樂保留檔案的個別備份複本。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="b8d9b-111">通話駐留應用程式的自訂音樂保留檔案會儲存在該池的檔案存放區中。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="b8d9b-112">若要將文件庫檔案存放區中的音訊檔案複製到商務用 Skype Server 2019 檔案存放區, 請使用**Xcopy**命令及下列參數:</span><span class="sxs-lookup"><span data-stu-id="b8d9b-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="b8d9b-113">當所有自訂的音訊檔案都已複製到商務用 Skype Server 2019 檔案存放區時, 必須設定商務用 Skype Server 2019 池的通話駐留應用程式設定, 以及與舊版池子相關的通話駐留軌道範圍必須重新指派給商務用 Skype Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="b8d9b-114">[通話駐留] 應用程式設定包括拾取超時閾值、啟用或停用音樂、最大的呼叫挑選嘗試, 以及超時要求。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="b8d9b-115">您必須使用商務用 Skype Server Management Shell 來管理呼叫駐留應用程式設定, 以執行**CsCpsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="b8d9b-116">您無法使用商務用 Skype Server [控制台] 管理 [通話駐留應用程式設定]。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="b8d9b-117">重新設定通話公園服務設定</span><span class="sxs-lookup"><span data-stu-id="b8d9b-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="b8d9b-118">從商務用 Skype Server 2019 前端伺服器, 開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="b8d9b-119">在命令列中, 輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="b8d9b-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8d9b-120">如果您的商務用 Skype Server 2019 通話駐留應用程式設定與舊版設定相同, 您可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="b8d9b-121">如果針對商務用 Skype Server 2019 與舊版環境, 通話駐留應用程式設定會有所不同, 請使用下面的 Cmdlet 做為範本來更新這些變更。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="b8d9b-122">若要將所有通話駐留軌道範圍從舊版池中重新指派到商務用 Skype Server 2019, 您可以使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理] 命令介面。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b8d9b-123">使用商務用 Skype Server 的 [控制台] 中的 [重新指派所有通話駐留軌道] 範圍</span><span class="sxs-lookup"><span data-stu-id="b8d9b-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b8d9b-124">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="b8d9b-125">在左窗格中, 選取 [**語音功能**]。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="b8d9b-126">選取 [**通話駐留**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="b8d9b-127">針對指派給舊版池中的每個通話駐留軌道範圍, 請編輯**目的地伺服器**設定的 FQDN, 然後選取將處理通話駐留要求的商務用 Skype server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="b8d9b-128">選取 [**確認**], 儲存變更。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b8d9b-129">使用商務用 Skype Server Management Shell 重新分派所有通話駐留軌道的範圍</span><span class="sxs-lookup"><span data-stu-id="b8d9b-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b8d9b-130">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="b8d9b-131">在命令列中, 輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="b8d9b-131">At the command line, type the following:</span></span>

   ```
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="b8d9b-132">這個 Cmdlet 會列出部署中所有的通話駐留軌道的範圍。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="b8d9b-133">所有設定為舊版池的**CallParkServiceId**和**CallParkServerFqdn**參數的通話駐留軌道式, 都必須重新指派。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="b8d9b-134">若要將舊版通話駐留軌道範圍重新指派給商務用 Skype Server 2019, 請在命令列中輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="b8d9b-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="b8d9b-135">將所有呼叫公園軌道範圍重新指派給商務用 Skype Server 2019 池之後, 通話駐留應用程式的遷移程式將會完成, 而商務用 Skype Server 2019 池會處理所有未來的通話駐留要求。</span><span class="sxs-lookup"><span data-stu-id="b8d9b-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


