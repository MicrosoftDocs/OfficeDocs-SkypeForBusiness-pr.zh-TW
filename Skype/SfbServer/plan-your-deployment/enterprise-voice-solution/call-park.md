---
title: 在商務用 Skype 中規劃電話寄存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 在商務用 Skype Server Enterprise Voice 中規劃通話寄存, 這可讓通話保持通話, 並將通話轉移至部門。 包括容量規劃、支援的通話, 以及支援的用戶端。
ms.openlocfilehash: 3272efe89ac995b304d96ad7ce5660144641073b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187768"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="0a301-104">在商務用 Skype 中規劃電話寄存</span><span class="sxs-lookup"><span data-stu-id="0a301-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="0a301-105">在商務用 Skype Server Enterprise Voice 中規劃通話寄存, 這可讓通話保持通話, 並將通話轉移至部門。</span><span class="sxs-lookup"><span data-stu-id="0a301-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="0a301-106">包括容量規劃、支援的通話, 以及支援的用戶端。</span><span class="sxs-lookup"><span data-stu-id="0a301-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="0a301-107">通話駐留應用程式可讓企業語音使用者執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="0a301-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="0a301-108">保留通話, 然後從同一個電話或另一個電話取回通話。</span><span class="sxs-lookup"><span data-stu-id="0a301-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="0a301-109">[保留通話] 可將來電轉接到部門或一般區域 (例如, 移至 [銷售部門] 或 [有共同區域電話的倉庫])。</span><span class="sxs-lookup"><span data-stu-id="0a301-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="0a301-110">保留通話, 並保留原始的應答電話供其他通話。</span><span class="sxs-lookup"><span data-stu-id="0a301-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="0a301-111">當使用者公園來電時, 商務用 Skype 伺服器會將來電轉接到暫時號碼 (稱為軌道), 通話會一直留在進行檢索或超時。商務用 Skype 伺服器會將軌道傳送給停用通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="0a301-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="0a301-112">若要取得寄存通話, 使用者可以撥打軌道編號, 或按一下交談視窗中的 [軌道] 連結或按鈕。</span><span class="sxs-lookup"><span data-stu-id="0a301-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="0a301-113">停用通話的使用者可以使用外部機制 (例如立即訊息 (IM) 或分頁系統), 通知某人使用外部機制來取得通話, 以將軌道編號傳達給其他人。</span><span class="sxs-lookup"><span data-stu-id="0a301-113">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="0a301-114">停用通話的使用者可以讓交談視窗保持開啟, 在檢索通話時接收通知。</span><span class="sxs-lookup"><span data-stu-id="0a301-114">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="0a301-115">由於軌道範圍是全域唯一的, 因此, 如果路由設定正確, 就可以從任何商務用 Skype Server 網站或 PBX 電話中檢索通話。</span><span class="sxs-lookup"><span data-stu-id="0a301-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="0a301-116">如果沒有人在可設定的時間內檢索呼叫, 來電會傳回寄存該通話的人。</span><span class="sxs-lookup"><span data-stu-id="0a301-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="0a301-117">如果該人員不接聽 ringback, 則會將來電轉接到回退目的地, 例如, 如果已設定, 就會傳送給接線員。</span><span class="sxs-lookup"><span data-stu-id="0a301-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="0a301-118">您可以將呼叫響鈴的次數設定為從1到十次轉接。</span><span class="sxs-lookup"><span data-stu-id="0a301-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="0a301-119">如果沒有人接聽轉接來電, 通話就會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0a301-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="0a301-120">檢索或斷開通話時, 會釋放軌道。</span><span class="sxs-lookup"><span data-stu-id="0a301-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="0a301-121">當您部署 [通話寄存] 時, 您必須為 [停止通話] 保留延伸號碼的範圍。</span><span class="sxs-lookup"><span data-stu-id="0a301-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="0a301-122">這些延伸必須是虛擬延伸: 沒有指派使用者或電話的延伸。</span><span class="sxs-lookup"><span data-stu-id="0a301-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="0a301-123">接著, 您可以將 [通話駐留軌道] 表格設定為延伸的範圍, 並指定哪個應用程式服務主持處理每個範圍的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="0a301-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="0a301-124">每個前端池在對應的後端伺服器上都有一個 [呼叫駐留] 資料表, 用來管理停在該池中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0a301-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="0a301-125">軌道範圍清單會儲存在中央管理存放區中, 並用於將軌道式路由到目的地池。</span><span class="sxs-lookup"><span data-stu-id="0a301-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="0a301-126">部署及設定通話駐留應用程式的每個商務用 Skype 伺服器池都可以有一或多個軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="0a301-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="0a301-127">在商務用 Skype Server 部署中, 軌道範圍必須全域唯一。</span><span class="sxs-lookup"><span data-stu-id="0a301-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="0a301-128">您也可以設定其他通話寄存設定, 例如, 如果電話被重新導向, 以及手機上的人員是否會聽到音樂, 請在停用時撥打。</span><span class="sxs-lookup"><span data-stu-id="0a301-128">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="0a301-129">您也可以指定在通話保留期間播放音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="0a301-129">You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a301-130">在商務用 Skype Server 災害復原程式中, 不會將通話駐留的自訂音樂保留式檔案備份, 如果上傳至該池的檔案遭到損毀、損毀或清除, 就會遺失。</span><span class="sxs-lookup"><span data-stu-id="0a301-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="0a301-131">針對通話駐留, 請務必針對您上傳的自訂音樂保留檔案保留一個單獨的備份複本。</span><span class="sxs-lookup"><span data-stu-id="0a301-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="0a301-132">通話駐留應用程式是企業語音的元件。</span><span class="sxs-lookup"><span data-stu-id="0a301-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="0a301-133">當您部署企業語音時, 通話寄存應用程式會自動安裝並啟用。</span><span class="sxs-lookup"><span data-stu-id="0a301-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="0a301-134">不過, 在您可以使用電話寄存前, 企業語音管理員必須設定它, 並透過語音原則為使用者啟用它。</span><span class="sxs-lookup"><span data-stu-id="0a301-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="0a301-135">部署與需求</span><span class="sxs-lookup"><span data-stu-id="0a301-135">Deployment and requirements</span></span>

<span data-ttu-id="0a301-136">當您部署企業語音時, 會自動安裝通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="0a301-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0a301-137">您可以透過設定語音原則來啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="0a301-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="0a301-138">軟體需求</span><span class="sxs-lookup"><span data-stu-id="0a301-138">Software requirements</span></span>

<span data-ttu-id="0a301-139">部署通話駐留的所有前端伺服器和標準版伺服器, 都必須針對執行 Windows Server 2008 R2 的伺服器安裝 windows Media 格式執行時間, 或執行 Windows Server 2012 或 Windows Server 的伺服器的 Microsoft Media Foundation2012 R2。</span><span class="sxs-lookup"><span data-stu-id="0a301-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="0a301-140">針對 Windows Server 2008 R2, Windows Media 格式執行時間已安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="0a301-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="0a301-141">Windows media 音訊 (.wma) 檔案需要 windows Media Format 執行時間或 Microsoft 媒體基礎, 這些檔案會通話駐留的暫停播放。</span><span class="sxs-lookup"><span data-stu-id="0a301-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="0a301-142">埠需求</span><span class="sxs-lookup"><span data-stu-id="0a301-142">Port requirements</span></span>

<span data-ttu-id="0a301-143">通話駐留應用程式使用**埠 5075**進行 SIP 偵聽要求。</span><span class="sxs-lookup"><span data-stu-id="0a301-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0a301-144">此埠是預設設定, 您可以使用**CsApplicationServer** Cmdlet 進行變更。</span><span class="sxs-lookup"><span data-stu-id="0a301-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="0a301-145">如需此 Cmdlet 的詳細資訊, 請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="0a301-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="0a301-146">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="0a301-146">Audio File requirements</span></span>

<span data-ttu-id="0a301-147">通話駐留應用程式只支援 Windows Media 音訊 (.wma) 檔案, 以供等候音樂。</span><span class="sxs-lookup"><span data-stu-id="0a301-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="0a301-148">您可以使用 Microsoft Expression 編碼器4來自訂等候音樂的檔案。</span><span class="sxs-lookup"><span data-stu-id="0a301-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="0a301-149">若要下載運算式編碼器 4, 請參閱「[運算式編碼器 4](https://go.microsoft.com/fwlink/p/?linkId=202843)」。</span><span class="sxs-lookup"><span data-stu-id="0a301-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="0a301-150">使用工具將檔案轉換為 .wma 格式。</span><span class="sxs-lookup"><span data-stu-id="0a301-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="0a301-151">通話駐留音樂保留盤案的建議格式是媒體音訊9、44 kHz、16位、單聲道、CBR、32 kbps。</span><span class="sxs-lookup"><span data-stu-id="0a301-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a301-152">已轉換的檔案只能在 16 kHz 的電話上播放, 即使該檔案是在 44 kHz 錄製。</span><span class="sxs-lookup"><span data-stu-id="0a301-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="0a301-153">支援的用戶端和通話</span><span class="sxs-lookup"><span data-stu-id="0a301-153">Supported clients and calls</span></span>

<span data-ttu-id="0a301-154">通話駐留支援下列用戶端和呼叫類型</span><span class="sxs-lookup"><span data-stu-id="0a301-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="0a301-155">支援停用通話的用戶端</span><span class="sxs-lookup"><span data-stu-id="0a301-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="0a301-156">來自任何 IP、私人分支 exchange (PBX)、公用交換電話網絡 (PSTN) 或行動電話的呼叫都可以停用。</span><span class="sxs-lookup"><span data-stu-id="0a301-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a301-157">只有音訊通話可以停用。</span><span class="sxs-lookup"><span data-stu-id="0a301-157">Only audio calls can be parked.</span></span> <span data-ttu-id="0a301-158">無法停用立即訊息和會議。</span><span class="sxs-lookup"><span data-stu-id="0a301-158">Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="0a301-159">下列用戶端可以使用通話駐留撥出電話:</span><span class="sxs-lookup"><span data-stu-id="0a301-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="0a301-160">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="0a301-160">Skype for Business</span></span>
    
- <span data-ttu-id="0a301-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0a301-161">Lync 2013</span></span>
    
- <span data-ttu-id="0a301-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0a301-162">Lync 2010</span></span>
    
- <span data-ttu-id="0a301-163">Lync 2010 助理</span><span class="sxs-lookup"><span data-stu-id="0a301-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="0a301-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="0a301-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="0a301-165">行動電話無法使用通話駐留撥出電話。</span><span class="sxs-lookup"><span data-stu-id="0a301-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="0a301-166">支援的用戶端檢索通話</span><span class="sxs-lookup"><span data-stu-id="0a301-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="0a301-167">軌道範圍是設定為虛擬延伸的區塊 (不含指派使用者或電話的延伸)。</span><span class="sxs-lookup"><span data-stu-id="0a301-167">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="0a301-168">當您將 [軌道式] 設定為 [虛擬延伸] 時, 行動電話和 PSTN 手機無法取得停用的通話。</span><span class="sxs-lookup"><span data-stu-id="0a301-168">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="0a301-169">同盟使用者無法取得停用的通話。</span><span class="sxs-lookup"><span data-stu-id="0a301-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="0a301-170">下列用戶端可以檢索寄存在通話寄存上的通話:</span><span class="sxs-lookup"><span data-stu-id="0a301-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="0a301-171">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="0a301-171">Skype for Business</span></span>
    
- <span data-ttu-id="0a301-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0a301-172">Lync 2013</span></span>
    
- <span data-ttu-id="0a301-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0a301-173">Lync 2010</span></span>
    
- <span data-ttu-id="0a301-174">Lync 2010 助理</span><span class="sxs-lookup"><span data-stu-id="0a301-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="0a301-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="0a301-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="0a301-176">IP 通用區域電話</span><span class="sxs-lookup"><span data-stu-id="0a301-176">IP common area phones</span></span>
    
- <span data-ttu-id="0a301-177">連線至商務用 Skype Server 基礎結構的非 IP 電話, 包括通用的局域網和私人分支 exchange (PBX) 電話</span><span class="sxs-lookup"><span data-stu-id="0a301-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="0a301-178">通話駐留容量規劃</span><span class="sxs-lookup"><span data-stu-id="0a301-178">Call Park capacity planning</span></span>

<span data-ttu-id="0a301-179">下表說明您可以用來做為容量規劃需求基礎的通話駐留使用者模型。</span><span class="sxs-lookup"><span data-stu-id="0a301-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0a301-180">請記住, 對於災難復原容量規劃, 配對池的每個池都應該能夠處理兩個池中的通話駐留服務的工作負荷。</span><span class="sxs-lookup"><span data-stu-id="0a301-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="0a301-181">**通話駐留使用者模型**</span><span class="sxs-lookup"><span data-stu-id="0a301-181">**Call Park User Model**</span></span>

|<span data-ttu-id="0a301-182">**衡量**</span><span class="sxs-lookup"><span data-stu-id="0a301-182">**Metric**</span></span>|<span data-ttu-id="0a301-183">**每個前臺端<br/>池 (含8個前端伺服器)**</span><span class="sxs-lookup"><span data-stu-id="0a301-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="0a301-184">**每個標準版 server**</span><span class="sxs-lookup"><span data-stu-id="0a301-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a301-185">公園工資率</span><span class="sxs-lookup"><span data-stu-id="0a301-185">Park rate</span></span>  <br/> |<span data-ttu-id="0a301-186">每分鐘8筆</span><span class="sxs-lookup"><span data-stu-id="0a301-186">8 per minute</span></span>  <br/> |<span data-ttu-id="0a301-187">每分鐘1</span><span class="sxs-lookup"><span data-stu-id="0a301-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="0a301-188">檢索暫停的通話頻率</span><span class="sxs-lookup"><span data-stu-id="0a301-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="0a301-189">每分鐘8筆</span><span class="sxs-lookup"><span data-stu-id="0a301-189">8 per minute</span></span>  <br/> |<span data-ttu-id="0a301-190">每分鐘1</span><span class="sxs-lookup"><span data-stu-id="0a301-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="0a301-191">平均公園持續時間</span><span class="sxs-lookup"><span data-stu-id="0a301-191">Average park duration</span></span>  <br/> |<span data-ttu-id="0a301-192">60秒</span><span class="sxs-lookup"><span data-stu-id="0a301-192">60 seconds</span></span>  <br/> |<span data-ttu-id="0a301-193">60秒</span><span class="sxs-lookup"><span data-stu-id="0a301-193">60 seconds</span></span>  <br/> |
   

