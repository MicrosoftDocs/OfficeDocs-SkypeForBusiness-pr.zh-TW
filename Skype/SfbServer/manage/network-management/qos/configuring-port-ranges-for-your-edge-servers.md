---
title: 設定 Edge Server 的埠範圍和服務品質
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文說明如何設定 Edge Server 的埠範圍，以及如何為您的 A/V Edge Server 設定服務品質原則。
ms.openlocfilehash: c88f784fe1956fa16b8464caa4f9f26e5c61005e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832903"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="52cbb-103">在商務用 Skype Server 中設定 Edge Server 的埠範圍和服務品質原則</span><span class="sxs-lookup"><span data-stu-id="52cbb-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="52cbb-104">本文說明如何設定 Edge Server 的埠範圍，以及如何為您的 A/V Edge Server 設定服務品質原則。</span><span class="sxs-lookup"><span data-stu-id="52cbb-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="52cbb-105">設定埠範圍</span><span class="sxs-lookup"><span data-stu-id="52cbb-105">Configure port ranges</span></span>

<span data-ttu-id="52cbb-106">透過 Edge server，您不需要為音訊、影片和應用程式共用設定個別的埠範圍;同樣地，Edge server 所用的埠範圍不必比對您的會議、應用程式及轉送伺服器所使用的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="52cbb-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="52cbb-107">在繼續進行範例之前，請務必強調此選項存在時，建議您不要變更埠範圍，因為當您移出50000埠範圍時，可能會對某些案例產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="52cbb-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="52cbb-108">例如，假設您已設定會議、應用程式以及中繼伺服器以使用這些連接埠範圍：</span><span class="sxs-lookup"><span data-stu-id="52cbb-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52cbb-109">封包類型</span><span class="sxs-lookup"><span data-stu-id="52cbb-109">Packet Type</span></span></th>
<th><span data-ttu-id="52cbb-110">起始連接埠</span><span class="sxs-lookup"><span data-stu-id="52cbb-110">Starting Port</span></span></th>
<th><span data-ttu-id="52cbb-111">已保留連接埠數目</span><span class="sxs-lookup"><span data-stu-id="52cbb-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52cbb-112">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="52cbb-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="52cbb-113">40803</span><span class="sxs-lookup"><span data-stu-id="52cbb-113">40803</span></span></p></td>
<td><p><span data-ttu-id="52cbb-114">8348</span><span class="sxs-lookup"><span data-stu-id="52cbb-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52cbb-115">音訊</span><span class="sxs-lookup"><span data-stu-id="52cbb-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="52cbb-116">49152</span><span class="sxs-lookup"><span data-stu-id="52cbb-116">49152</span></span></p></td>
<td><p><span data-ttu-id="52cbb-117">8348</span><span class="sxs-lookup"><span data-stu-id="52cbb-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52cbb-118">影片</span><span class="sxs-lookup"><span data-stu-id="52cbb-118">Video</span></span></p></td>
<td><p><span data-ttu-id="52cbb-119">57500</span><span class="sxs-lookup"><span data-stu-id="52cbb-119">57500</span></span></p></td>
<td><p><span data-ttu-id="52cbb-120">8034</span><span class="sxs-lookup"><span data-stu-id="52cbb-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52cbb-121"><strong>總數</strong></span><span class="sxs-lookup"><span data-stu-id="52cbb-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="52cbb-122">24730</span><span class="sxs-lookup"><span data-stu-id="52cbb-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52cbb-123">如您所見，音訊、影片和應用程式共用的埠範圍會從埠40803開始，並包含24732埠的總數。</span><span class="sxs-lookup"><span data-stu-id="52cbb-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="52cbb-124">如果您願意，您可以在商務用 Skype Server 管理命令介面中執行類似下列的命令，以設定指定的 Edge Server 使用這些整體埠值：</span><span class="sxs-lookup"><span data-stu-id="52cbb-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="52cbb-125">或者，使用下列命令以在組織中同時設定所有 Edge 伺服器：</span><span class="sxs-lookup"><span data-stu-id="52cbb-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="52cbb-126">您可以使用此商務用 Skype Server 管理命令介面命令來驗證 Edge server 的目前埠設定：</span><span class="sxs-lookup"><span data-stu-id="52cbb-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="52cbb-127">同樣地，我們確實提供這些選項，我們強烈建議您保留其為埠設定的內容。</span><span class="sxs-lookup"><span data-stu-id="52cbb-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="52cbb-128">設定 A/V Edge Server 的 QoS 原則</span><span class="sxs-lookup"><span data-stu-id="52cbb-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="52cbb-129">除了為會議伺服器、應用程式伺服器及中繼伺服器建立 QoS 原則，您也必須為 A/V Edge Server 的內部端建立音訊及視訊原則。</span><span class="sxs-lookup"><span data-stu-id="52cbb-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="52cbb-130">不過，在 Edge Server 上使用的原則，不同於在會議伺服器、應用程式伺服器及中繼伺服器上使用的原則。</span><span class="sxs-lookup"><span data-stu-id="52cbb-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="52cbb-131">針對會議、應用程式及轉送伺服器，您指定了來源埠範圍;透過 Edge server，您必須指定目的地埠範圍。</span><span class="sxs-lookup"><span data-stu-id="52cbb-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="52cbb-132">因此，您無法只將會議、應用程式及轉送伺服器 QoS 原則套用至 Edge server：這些原則根本無法運作。</span><span class="sxs-lookup"><span data-stu-id="52cbb-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="52cbb-133">反之，您必須建立新的原則，並將這些原則只套用到 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="52cbb-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="52cbb-134">下列程序說明如何在 Edge Server 上，建立可以用來管理服務品質的 Active Directory 群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="52cbb-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="52cbb-135">當然，您的 Edge Server 有可能是沒有 Active Directory 帳戶的獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="52cbb-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="52cbb-136">若是如此，您可以使用本機群組原則來代替 Active Directory 群組原則：唯一不同的是，您必須使用本機群組原則編輯器來建立這些本機原則，而且必須在每部 Edge Server 上個別建立相同的原則集。</span><span class="sxs-lookup"><span data-stu-id="52cbb-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="52cbb-137">若要在 Edge server 上啟動本機組策略編輯器，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="52cbb-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="52cbb-138">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="52cbb-139">在 [ **執行** ] 對話方塊中，輸入 **gpedit.msc**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="52cbb-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="52cbb-140">如果您要建立 Active Directory 型原則，應登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="52cbb-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="52cbb-141">在此情況下，請開啟 [群組原則管理] (按一下 [ **開始**]，指向 [系統 **管理工具**]，然後按一下 [ **群組原則管理**) ]，然後完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="52cbb-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="52cbb-142">在群組原則管理中，找出要用來建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="52cbb-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="52cbb-143">例如，如果您所有的商務用 Skype Server 電腦都位於名為商務用 Skype Server 的 OU 中，則應該在商務用 Skype Server OU 中建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="52cbb-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="52cbb-144">以滑鼠右鍵按一下適當的容器，然後按一下 [ **在這個網域中建立 GPO]，並在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="52cbb-145">在 [ **新增 GPO** ] 對話方塊的 [ **名稱** ] 方塊中，輸入新群組原則物件的名稱 (例如， **商務用 Skype Server 音訊**) ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="52cbb-146">以滑鼠右鍵按一下新建立的原則，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="52cbb-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="52cbb-147">從這裡開始，無論您是要建立 Active Directory 原則或本機原則，程序都一樣：</span><span class="sxs-lookup"><span data-stu-id="52cbb-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="52cbb-148">在群組原則管理編輯器或本機群組原則編輯器中，依序展開 [電腦設定]、[原則]、[Windows 設定]，以滑鼠右鍵按一下 [以原則為依據的 QoS]，然後按一下 [建立新原則]。</span><span class="sxs-lookup"><span data-stu-id="52cbb-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="52cbb-149">在 [**原則型 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱 (例如，**商務用 Skype Server 音訊**) 。</span><span class="sxs-lookup"><span data-stu-id="52cbb-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="52cbb-150">選取 [指定 DSCP 數值]，並將該值設為 **46**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="52cbb-151">將 [指定輸出節流閥速率] 保留未選取狀態，然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="52cbb-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="52cbb-152">在下一個頁面上，確定已選取 [ **所有應用程式** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="52cbb-153">此設定會指示網路尋找 DSCP 標示為 46 的所有封包，而不只是特定應用程式建立的封包。</span><span class="sxs-lookup"><span data-stu-id="52cbb-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="52cbb-154">在第三頁上，確定已選取 [ **所有來源 ip 位址** ] 和 [ **任何目的地 ip 位址** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="52cbb-155">這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。</span><span class="sxs-lookup"><span data-stu-id="52cbb-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="52cbb-156">在第四頁上，從 [選取此 QoS 原則套用的通訊協定] 下拉式清單中選取 [TCP 及 UDP]。</span><span class="sxs-lookup"><span data-stu-id="52cbb-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="52cbb-157">TCP (傳輸控制通訊協定) 和 UDP (使用者資料包通訊協定) 是商務用 Skype Server 及其用戶端應用程式最常使用的兩種網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="52cbb-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="52cbb-158">在 [指定目的地連接埠號碼] 標題底下，選取 [從此目的地連接埠或範圍]。</span><span class="sxs-lookup"><span data-stu-id="52cbb-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="52cbb-159">在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="52cbb-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="52cbb-160">例如，如果您將埠49152設定為音訊流量的埠57500，請輸入使用此格式的埠範圍： **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="52cbb-161">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-161">Click **Finish**.</span></span>

<span data-ttu-id="52cbb-162">在建立音訊流量的 QoS 原則之後，您應該先建立影片流量的第二個原則。</span><span class="sxs-lookup"><span data-stu-id="52cbb-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="52cbb-163">若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：</span><span class="sxs-lookup"><span data-stu-id="52cbb-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="52cbb-164">使用不同的 (和唯一的) 原則名稱 (例如， **商務用 Skype Server 影片**) 。</span><span class="sxs-lookup"><span data-stu-id="52cbb-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="52cbb-p113">將 DSCP 值設為 **34** 而不是 46。(請注意，DSCP 值不一定要使用 34。唯一的要求是用於視訊和音訊的 DSCP 值必須不同。)</span><span class="sxs-lookup"><span data-stu-id="52cbb-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="52cbb-168">使用先前設定的影片流量的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="52cbb-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="52cbb-169">例如，如果您有保留的埠57501到65535以取得影片，請將埠範圍設定為： **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="52cbb-170">再強調一次，這應該設為目的地連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="52cbb-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="52cbb-171">如果您決定建立用來管理應用程式共用流量的原則，則必須建立第三個原則，以進行下列替代：</span><span class="sxs-lookup"><span data-stu-id="52cbb-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="52cbb-172">使用不同的 (和唯一的) 原則名稱 (例如， **商務用 Skype Server 應用程式共用**) 。</span><span class="sxs-lookup"><span data-stu-id="52cbb-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="52cbb-p115">將 DSCP 值設為 **24** 而不是 46。(再強調一次，DSCP 值不一定要使用 24。唯一的要求是用於應用程式共用的 DSCP 值必須與視訊或音訊不同。)</span><span class="sxs-lookup"><span data-stu-id="52cbb-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="52cbb-176">使用先前設定的影片流量的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="52cbb-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="52cbb-177">例如，如果您有保留埠40803到49151以進行應用程式共用，請將埠範圍設定為： **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="52cbb-p117">必須在 Edge Server 上重新整理群組原則之後，您建立的新原則才會生效。雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="52cbb-p117">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="52cbb-180">您可以從商務用 Skype Server 或任何執行于系統管理員認證的命令視窗中執行此命令。</span><span class="sxs-lookup"><span data-stu-id="52cbb-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="52cbb-181">若要以系統管理員憑證執行命令視窗，請按一下 [開始]，以滑鼠右鍵按一下 [命令提示字元]，然後按一下 [以系統管理員身分執行]。</span><span class="sxs-lookup"><span data-stu-id="52cbb-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="52cbb-182">請注意，即使在執行 Gpudate.exe 之後，可能還是需要重新啟動 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="52cbb-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="52cbb-183">為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="52cbb-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="52cbb-184">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="52cbb-185">在 [ **執行** ] 對話方塊中，輸入 **regedit**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="52cbb-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="52cbb-186">在 [登錄編輯程式] 中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **系統**]，展開 [ **CurrentControlSet**]，展開 [ **服務**]，然後展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="52cbb-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="52cbb-187">以滑鼠右鍵按一下 [Tcpip]，指向 [新增]，然後按一下 [索引鍵]。</span><span class="sxs-lookup"><span data-stu-id="52cbb-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="52cbb-188">在建立新的登錄機碼之後，輸入 **QoS**，然後按 enter 重新命名機碼。</span><span class="sxs-lookup"><span data-stu-id="52cbb-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="52cbb-189">以滑鼠右鍵按一下 [QoS]，指向 [新增]，然後按一下 [字串值]。</span><span class="sxs-lookup"><span data-stu-id="52cbb-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="52cbb-190">在建立新的登錄值之後，請輸入 [ **不要使用 NLA**]，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="52cbb-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="52cbb-191">按兩下 [Do not use NLA]。</span><span class="sxs-lookup"><span data-stu-id="52cbb-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="52cbb-192">在 [**編輯字串**] 對話方塊的 [**數值資料**] 方塊中，輸入 **1** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="52cbb-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="52cbb-193">關閉 [登錄編輯程式]，然後重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="52cbb-193">Close the Registry Editor and reboot your computer.</span></span>
