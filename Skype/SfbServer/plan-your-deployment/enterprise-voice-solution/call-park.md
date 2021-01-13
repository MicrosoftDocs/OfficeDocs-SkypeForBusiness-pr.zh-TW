---
title: 在商務用 Skype 中規劃通話駐留
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 規劃商務用 Skype Server Enterprise Voice 中的通話駐留，讓通話保持通話，並將來電轉接至部門。 包括容量規劃、支援的通話，以及支援的用戶端。
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825923"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="dfab4-104">在商務用 Skype 中規劃通話駐留</span><span class="sxs-lookup"><span data-stu-id="dfab4-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="dfab4-105">規劃商務用 Skype Server Enterprise Voice 中的通話駐留，讓通話保持通話，並將來電轉接至部門。</span><span class="sxs-lookup"><span data-stu-id="dfab4-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="dfab4-106">包括容量規劃、支援的通話，以及支援的用戶端。</span><span class="sxs-lookup"><span data-stu-id="dfab4-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="dfab4-107">通話駐留應用程式可讓企業語音使用者執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="dfab4-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="dfab4-108">進行暫止通話，然後從相同電話或其他電話取得通話。</span><span class="sxs-lookup"><span data-stu-id="dfab4-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="dfab4-109">進行暫止通話，將其轉接至部門或一般區域 (例如，移至銷售部門或存在公共區域電話的倉庫) 。</span><span class="sxs-lookup"><span data-stu-id="dfab4-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="dfab4-110">保留通話，並將原始接聽電話保留空閒狀態供其他電話使用。</span><span class="sxs-lookup"><span data-stu-id="dfab4-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="dfab4-111">當使用者公園通話時，商務用 Skype 伺服器會將來電轉接到暫時號碼（稱為軌道），該呼叫會保留，直到被取回或超時為止。商務用 Skype 伺服器會將軌道傳送給停用通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="dfab4-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="dfab4-112">若要取得寄存通話，使用者可以撥打軌道號碼，或按一下 [交談] 視窗中的 [軌道] 連結或按鈕。</span><span class="sxs-lookup"><span data-stu-id="dfab4-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="dfab4-113">停用通話的使用者可以使用外部機制（如立即訊息 (IM) 或分頁系統）來通知人員取得通話，以與其他人溝通軌道號碼。</span><span class="sxs-lookup"><span data-stu-id="dfab4-113">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="dfab4-114">停用通話的使用者可以讓 [交談] 視窗保持開啟，以在檢索來電時收到通知。</span><span class="sxs-lookup"><span data-stu-id="dfab4-114">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="dfab4-115">因為軌道範圍是全域唯一的，所以如果路由設定正確，可以從任何商務用 Skype Server 網站或 PBX 電話取回通話。</span><span class="sxs-lookup"><span data-stu-id="dfab4-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="dfab4-116">如果沒有人在可設定的時間內取回通話，則呼叫會傳回寄存其的人員。</span><span class="sxs-lookup"><span data-stu-id="dfab4-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="dfab4-117">如果此人沒有回答回電，則會將來電轉接至 fallback 目的地（例如，如果已設定，則為操作員）。</span><span class="sxs-lookup"><span data-stu-id="dfab4-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="dfab4-118">您可以設定來電響鈴的次數，再從一到十次轉接。</span><span class="sxs-lookup"><span data-stu-id="dfab4-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="dfab4-119">如果沒有人接聽轉接的電話，則通話會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="dfab4-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="dfab4-120">檢索或中斷通話呼叫時，會釋放軌道。</span><span class="sxs-lookup"><span data-stu-id="dfab4-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="dfab4-121">當您部署通話駐留時，您必須保留駐留通話的分機號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="dfab4-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="dfab4-122">這些分機必須是虛擬分機：沒有指派使用者或電話的分機號碼。</span><span class="sxs-lookup"><span data-stu-id="dfab4-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="dfab4-123">然後，您可以使用分機號碼範圍設定通話駐留軌道表格，並指定哪些應用程式服務主控處理每個範圍的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="dfab4-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="dfab4-124">每個前端集區在對應的後端伺服器上都有一個呼叫駐留表，用來管理集區上寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="dfab4-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="dfab4-125">軌道範圍的清單儲存在中央管理存放區中，用來將軌道式路由傳送至目的地集區。</span><span class="sxs-lookup"><span data-stu-id="dfab4-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="dfab4-126">部署及設定通話駐留應用程式的每個商務用 Skype 伺服器集區，都可以有一或多個軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="dfab4-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="dfab4-127">軌道範圍必須在整個商務用 Skype Server 部署中全域唯一。</span><span class="sxs-lookup"><span data-stu-id="dfab4-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="dfab4-128">您也可以設定其他通話駐留設定，例如，在通話超時的位置，以及電話上的人員是否會在寄存時，是否會聽到音樂。</span><span class="sxs-lookup"><span data-stu-id="dfab4-128">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="dfab4-129">您也可以在通話處於保留狀態時，指定要播放的音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="dfab4-129">You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dfab4-130">在商務用 Skype 伺服器的嚴重損壞復原過程中，不會備份通話駐留的自訂音樂暫止檔案，而且如果上傳至集區的檔案損毀、損毀或清除，將會遺失。</span><span class="sxs-lookup"><span data-stu-id="dfab4-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="dfab4-131">請永遠為通話保留，保留您為通話保留所上傳之自訂音樂暫止檔案的個別備份副本。</span><span class="sxs-lookup"><span data-stu-id="dfab4-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="dfab4-132">通話駐留應用程式是 Enterprise Voice 的元件。</span><span class="sxs-lookup"><span data-stu-id="dfab4-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="dfab4-133">當您部署企業語音時，會自動安裝通話駐留應用程式並加以啟用。</span><span class="sxs-lookup"><span data-stu-id="dfab4-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="dfab4-134">不過，您必須先設定企業語音管理員，並透過語音原則為使用者啟用通話駐留，才可使用通話保留。</span><span class="sxs-lookup"><span data-stu-id="dfab4-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="dfab4-135">部署和需求</span><span class="sxs-lookup"><span data-stu-id="dfab4-135">Deployment and requirements</span></span>

<span data-ttu-id="dfab4-136">當您部署企業語音時，會自動安裝通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="dfab4-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="dfab4-137">您可以透過設定語音原則來啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="dfab4-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="dfab4-138">軟體需求</span><span class="sxs-lookup"><span data-stu-id="dfab4-138">Software requirements</span></span>

<span data-ttu-id="dfab4-139">部署通話駐留的所有前端伺服器和 Standard Edition 伺服器都必須為執行 Windows Server 2008 R2 的伺服器安裝 Windows Media Format Runtime （或執行 Windows Server 2012 或 Windows Server 2012 R2 之伺服器的 Microsoft Media Foundation）。</span><span class="sxs-lookup"><span data-stu-id="dfab4-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="dfab4-140">若為 Windows Server 2008 R2，Windows Media Format Runtime 會安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="dfab4-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="dfab4-141">Windows media Audio ( 的 windows Media Format Runtime 或 Microsoft Media Foundation 是必要的功能。) 通話駐留的檔案會對等候音樂播放。</span><span class="sxs-lookup"><span data-stu-id="dfab4-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="dfab4-142">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="dfab4-142">Port requirements</span></span>

<span data-ttu-id="dfab4-143">通話駐留應用程式使用 **埠 5075**  進行 SIP 聆聽要求。</span><span class="sxs-lookup"><span data-stu-id="dfab4-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dfab4-144">此連接埠為預設設定，可使用 **Set-CsApplicationServer** Cmdlet 予以變更。</span><span class="sxs-lookup"><span data-stu-id="dfab4-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="dfab4-145">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="dfab4-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="dfab4-146">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="dfab4-146">Audio File requirements</span></span>

<span data-ttu-id="dfab4-147">通話駐留應用程式僅支援 Windows Media Audio ( 的 wma) 檔案用於等候音樂。</span><span class="sxs-lookup"><span data-stu-id="dfab4-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="dfab4-148">您可以使用 Microsoft Expression Encoder 4 自訂等候音樂的檔案。</span><span class="sxs-lookup"><span data-stu-id="dfab4-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="dfab4-149">若要下載運算式編碼器4，請參閱   ["運算式編碼器 4"](https://go.microsoft.com/fwlink/p/?linkId=202843)。</span><span class="sxs-lookup"><span data-stu-id="dfab4-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="dfab4-150">使用此工具可將檔案轉換成 .wma 格式。</span><span class="sxs-lookup"><span data-stu-id="dfab4-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="dfab4-151">通話駐留等候音樂檔案的建議格式為 Media Audio 9、44 kHz、16 位元、Mono、CBR、32 kbps。</span><span class="sxs-lookup"><span data-stu-id="dfab4-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dfab4-152">轉換後的檔案只能以 16 kHz 音頻在電話中播放，即使檔案是以 44 kHz 音頻錄製也一樣。</span><span class="sxs-lookup"><span data-stu-id="dfab4-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="dfab4-153">支援的用戶端和通話</span><span class="sxs-lookup"><span data-stu-id="dfab4-153">Supported clients and calls</span></span>

<span data-ttu-id="dfab4-154">通話駐留支援下列用戶端和通話類型</span><span class="sxs-lookup"><span data-stu-id="dfab4-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="dfab4-155">支援駐留通話的用戶端</span><span class="sxs-lookup"><span data-stu-id="dfab4-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="dfab4-156">來自任何 IP、專用交換機 (PBX) 、公用交換電話網路 (PSTN) 或行動電話可以寄存的電話。</span><span class="sxs-lookup"><span data-stu-id="dfab4-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dfab4-157">只有音訊通話可以寄存。</span><span class="sxs-lookup"><span data-stu-id="dfab4-157">Only audio calls can be parked.</span></span> <span data-ttu-id="dfab4-158">立即訊息和會議無法停用。</span><span class="sxs-lookup"><span data-stu-id="dfab4-158">Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="dfab4-159">下列用戶端可以將通話駐留用於駐留通話：</span><span class="sxs-lookup"><span data-stu-id="dfab4-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="dfab4-160">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="dfab4-160">Skype for Business</span></span>
    
- <span data-ttu-id="dfab4-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="dfab4-161">Lync 2013</span></span>
    
- <span data-ttu-id="dfab4-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="dfab4-162">Lync 2010</span></span>
    
- <span data-ttu-id="dfab4-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="dfab4-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="dfab4-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="dfab4-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="dfab4-165">行動電話無法將通話駐留用於寄存通話。</span><span class="sxs-lookup"><span data-stu-id="dfab4-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="dfab4-166">支援檢索呼叫的用戶端</span><span class="sxs-lookup"><span data-stu-id="dfab4-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="dfab4-167">軌道範圍會設定為不需要指派使用者或電話) 的虛擬分機區塊 (擴充。</span><span class="sxs-lookup"><span data-stu-id="dfab4-167">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="dfab4-168">當您將軌道式設定為虛擬分機時，行動電話和 PSTN 電話便無法檢索寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="dfab4-168">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="dfab4-169">同盟使用者無法檢索寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="dfab4-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="dfab4-170">下列用戶端可以檢索寄存在通話駐留上的通話：</span><span class="sxs-lookup"><span data-stu-id="dfab4-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="dfab4-171">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="dfab4-171">Skype for Business</span></span>
    
- <span data-ttu-id="dfab4-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="dfab4-172">Lync 2013</span></span>
    
- <span data-ttu-id="dfab4-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="dfab4-173">Lync 2010</span></span>
    
- <span data-ttu-id="dfab4-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="dfab4-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="dfab4-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="dfab4-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="dfab4-176">IP 公共區域電話</span><span class="sxs-lookup"><span data-stu-id="dfab4-176">IP common area phones</span></span>
    
- <span data-ttu-id="dfab4-177">連線至商務用 Skype 伺服器基礎結構的非 IP 電話，包括通用區域電話和專用交換機 (PBX) 電話</span><span class="sxs-lookup"><span data-stu-id="dfab4-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="dfab4-178">通話駐留容量規劃</span><span class="sxs-lookup"><span data-stu-id="dfab4-178">Call Park capacity planning</span></span>

<span data-ttu-id="dfab4-179">下表說明您可以用來作為容量規劃需求基礎的通話駐留使用者模型。</span><span class="sxs-lookup"><span data-stu-id="dfab4-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dfab4-180">請記住，針對嚴重損壞修復容量規劃，配對集區的每個集區都應該可以處理兩個集區中的通話駐留服務工作負載。</span><span class="sxs-lookup"><span data-stu-id="dfab4-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="dfab4-181">**通話駐留使用者模型**</span><span class="sxs-lookup"><span data-stu-id="dfab4-181">**Call Park User Model**</span></span>

|<span data-ttu-id="dfab4-182">**計量**</span><span class="sxs-lookup"><span data-stu-id="dfab4-182">**Metric**</span></span>|<span data-ttu-id="dfab4-183">**每個前端伺服器集區  <br/>  (8 部前端伺服器)**</span><span class="sxs-lookup"><span data-stu-id="dfab4-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="dfab4-184">**每個 Standard Edition server**</span><span class="sxs-lookup"><span data-stu-id="dfab4-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dfab4-185">駐留率</span><span class="sxs-lookup"><span data-stu-id="dfab4-185">Park rate</span></span>  <br/> |<span data-ttu-id="dfab4-186">每分鐘 8 個</span><span class="sxs-lookup"><span data-stu-id="dfab4-186">8 per minute</span></span>  <br/> |<span data-ttu-id="dfab4-187">每分鐘 1 個</span><span class="sxs-lookup"><span data-stu-id="dfab4-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="dfab4-188">擷取駐留通話率</span><span class="sxs-lookup"><span data-stu-id="dfab4-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="dfab4-189">每分鐘 8 個</span><span class="sxs-lookup"><span data-stu-id="dfab4-189">8 per minute</span></span>  <br/> |<span data-ttu-id="dfab4-190">每分鐘 1 個</span><span class="sxs-lookup"><span data-stu-id="dfab4-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="dfab4-191">平均駐留持續時間</span><span class="sxs-lookup"><span data-stu-id="dfab4-191">Average park duration</span></span>  <br/> |<span data-ttu-id="dfab4-192">60 秒</span><span class="sxs-lookup"><span data-stu-id="dfab4-192">60 seconds</span></span>  <br/> |<span data-ttu-id="dfab4-193">60 秒</span><span class="sxs-lookup"><span data-stu-id="dfab4-193">60 seconds</span></span>  <br/> |
   

