---
title: 為邊緣伺服器設定埠範圍和服務品質
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文說明如何設定邊緣伺服器的埠範圍，以及如何設定您的 A/V 邊緣伺服器的服務品質原則。
ms.openlocfilehash: 5762cb6861552696f160dfe69459c357f6b63452
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817432"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="f1368-103">在商務用 Skype Server 中針對 Edge 伺服器設定埠範圍和服務品質原則</span><span class="sxs-lookup"><span data-stu-id="f1368-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="f1368-104">本文說明如何設定邊緣伺服器的埠範圍，以及如何設定您的 A/V 邊緣伺服器的服務品質原則。</span><span class="sxs-lookup"><span data-stu-id="f1368-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="f1368-105">設定埠範圍</span><span class="sxs-lookup"><span data-stu-id="f1368-105">Configure port ranges</span></span>

<span data-ttu-id="f1368-106">有了 Edge 伺服器，您就不需要針對音訊、影片和應用程式共用設定個別的埠範圍;同樣地，邊緣伺服器所用的埠範圍不一定要與您的會議、應用程式及中繼伺服器所使用的埠範圍相符。</span><span class="sxs-lookup"><span data-stu-id="f1368-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="f1368-107">在開始使用我們的範例之前，請務必先將這個選項提供給您，但我們建議您不要變更埠範圍，因為如果您移出50000埠範圍，就可能會對某些案例造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="f1368-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="f1368-108">例如，假設您已將會議、應用程式和中繼伺服器設定為使用這些埠範圍：</span><span class="sxs-lookup"><span data-stu-id="f1368-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1368-109">資料包類型</span><span class="sxs-lookup"><span data-stu-id="f1368-109">Packet Type</span></span></th>
<th><span data-ttu-id="f1368-110">起始埠</span><span class="sxs-lookup"><span data-stu-id="f1368-110">Starting Port</span></span></th>
<th><span data-ttu-id="f1368-111">保留的埠數</span><span class="sxs-lookup"><span data-stu-id="f1368-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1368-112">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="f1368-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="f1368-113">40803</span><span class="sxs-lookup"><span data-stu-id="f1368-113">40803</span></span></p></td>
<td><p><span data-ttu-id="f1368-114">8348</span><span class="sxs-lookup"><span data-stu-id="f1368-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1368-115">音訊</span><span class="sxs-lookup"><span data-stu-id="f1368-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="f1368-116">49152</span><span class="sxs-lookup"><span data-stu-id="f1368-116">49152</span></span></p></td>
<td><p><span data-ttu-id="f1368-117">8348</span><span class="sxs-lookup"><span data-stu-id="f1368-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1368-118">顯示器</span><span class="sxs-lookup"><span data-stu-id="f1368-118">Video</span></span></p></td>
<td><p><span data-ttu-id="f1368-119">57500</span><span class="sxs-lookup"><span data-stu-id="f1368-119">57500</span></span></p></td>
<td><p><span data-ttu-id="f1368-120">8034</span><span class="sxs-lookup"><span data-stu-id="f1368-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1368-121"><strong>本壘</strong></span><span class="sxs-lookup"><span data-stu-id="f1368-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="f1368-122">24730</span><span class="sxs-lookup"><span data-stu-id="f1368-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f1368-123">如您所見，音訊、影片和應用程式共用的埠範圍是從埠40803開始，並包含總共24732個埠。</span><span class="sxs-lookup"><span data-stu-id="f1368-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="f1368-124">如果您想要的話，您可以將指定的邊緣伺服器設定為使用這些整體埠值，方法是從商務用 Skype Server 管理命令介面中執行如下的命令：</span><span class="sxs-lookup"><span data-stu-id="f1368-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="f1368-125">或者，使用下列命令同時設定貴組織中的所有邊緣伺服器：</span><span class="sxs-lookup"><span data-stu-id="f1368-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="f1368-126">您可以使用此商務用 Skype Server Management Shell 命令來驗證邊緣伺服器的目前埠設定：</span><span class="sxs-lookup"><span data-stu-id="f1368-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="f1368-127">同樣地，雖然我們確實提供這些選項，但我們強烈建議您將它們留給埠配置。</span><span class="sxs-lookup"><span data-stu-id="f1368-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="f1368-128">為您的 A/V 邊緣伺服器設定 QoS 原則</span><span class="sxs-lookup"><span data-stu-id="f1368-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="f1368-129">除了為您的會議、應用程式和中繼伺服器建立 QoS 原則之外，您還必須為 A/V 邊緣伺服器的內部端建立音訊與影片原則。</span><span class="sxs-lookup"><span data-stu-id="f1368-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="f1368-130">不過，在 Edge 伺服器上使用的原則與在您的會議、應用程式和中繼伺服器上使用的原則不同。</span><span class="sxs-lookup"><span data-stu-id="f1368-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="f1368-131">針對會議、應用程式及中繼伺服器，您指定了來源埠範圍;有了 Edge 伺服器，您必須指定目的地埠範圍。</span><span class="sxs-lookup"><span data-stu-id="f1368-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="f1368-132">因此，您無法直接將會議、應用程式和中繼伺服器 QoS 原則套用到您的邊緣伺服器：這些原則根本無法運作。</span><span class="sxs-lookup"><span data-stu-id="f1368-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="f1368-133">相反地，您必須建立新的原則，並將這些原則只套用到 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1368-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="f1368-134">下列程式說明建立 Active Directory 群組原則物件的程式，這些物件可用於管理 Edge 伺服器上的服務品質。</span><span class="sxs-lookup"><span data-stu-id="f1368-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="f1368-135">當然，您的邊緣伺服器可能是不具備 Active Directory 帳戶的獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1368-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="f1368-136">如果是這種情況，您可以使用本機組策略，而不是 Active Directory 群組原則：唯一的差別是，您必須使用本機組策略編輯器來建立這些本機原則，而且必須在每個 Edge 伺服器上分別建立相同的原則組。</span><span class="sxs-lookup"><span data-stu-id="f1368-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="f1368-137">若要在 Edge 伺服器上啟動本機組策略編輯器，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f1368-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="f1368-138">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="f1368-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="f1368-139">在 [**執行**] 對話方塊中，輸入 [ **gpedit.msc**]，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="f1368-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="f1368-140">如果您要建立 Active Directory 的原則，您應該登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="f1368-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="f1368-141">在這種情況下，請開啟 [群組原則管理] （按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**群組原則管理**]），然後完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f1368-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="f1368-142">在 [群組原則管理] 中，找出要建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="f1368-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="f1368-143">例如，如果您所有的商務用 Skype Server 電腦都位於名為商務用 Skype Server 的 OU 中，則應該在商務用 Skype Server OU 中建立新原則。</span><span class="sxs-lookup"><span data-stu-id="f1368-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="f1368-144">以滑鼠右鍵按一下適當的容器，然後按一下 [**在這個網域建立 GPO]，然後在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="f1368-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="f1368-145">在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中，輸入新群組原則物件的名稱（例如商務用**Skype Server 音訊**），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f1368-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="f1368-146">以滑鼠右鍵按一下新建立的原則，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="f1368-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="f1368-147">無論您是建立 Active Directory 原則或本機原則，此程式都是相同的：</span><span class="sxs-lookup"><span data-stu-id="f1368-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="f1368-148">在 [群組原則管理編輯器] 或 [本機組策略編輯器] 中，展開 [**電腦**設定]，展開 [**原則**]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [**原則式 QoS**]，然後按一下 [**建立新策略**]。</span><span class="sxs-lookup"><span data-stu-id="f1368-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="f1368-149">在 [**原則式 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱（例如**商務用 Skype Server 音訊**）。</span><span class="sxs-lookup"><span data-stu-id="f1368-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="f1368-150">選取 [**指定 DSCP 值**]，然後將值設定為**46**。</span><span class="sxs-lookup"><span data-stu-id="f1368-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="f1368-151">[離開]**指定輸出限制率**未選取，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f1368-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="f1368-152">在下一頁上，確認已選取 [**所有應用程式**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f1368-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="f1368-153">此設定會指示網路尋找 DSCP 標記為46的所有資料包，而不只是特定應用程式所建立的資料包。</span><span class="sxs-lookup"><span data-stu-id="f1368-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="f1368-154">在第三個頁面上，確認已選取 [**所有來源 ip 位址**] 和 [**任何目的地 ip 位址**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f1368-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="f1368-155">這兩項設定可確保無論哪些電腦（IP 位址）傳送這些資料包，以及哪些電腦（IP 位址）會接收那些資料包，都會管理資料包。</span><span class="sxs-lookup"><span data-stu-id="f1368-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="f1368-156">在第4頁，從 [**選取此 QoS 原則適用**于] 下拉式清單中選取 [ **TCP 和 UDP** ]。</span><span class="sxs-lookup"><span data-stu-id="f1368-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="f1368-157">TCP （傳輸控制通訊協定）和 UDP （使用者資料包通訊協定）是商務用 Skype Server 及其用戶端應用程式最常用的兩種網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="f1368-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="f1368-158">在 [標題] 底下**指定目的地埠號**，選取 [**從此目的地埠或範圍**]。</span><span class="sxs-lookup"><span data-stu-id="f1368-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="f1368-159">在隨附的文字方塊中，輸入為音訊廣播保留的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="f1368-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="f1368-160">例如，如果您是透過埠57500將埠49152保留音訊流量，請輸入使用此格式的埠範圍： **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="f1368-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="f1368-161">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f1368-161">Click **Finish**.</span></span>

<span data-ttu-id="f1368-162">在您建立音訊流量的 QoS 原則之後，您應該為影片流量建立第二個原則。</span><span class="sxs-lookup"><span data-stu-id="f1368-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="f1368-163">若要建立影片的原則，請遵循您在建立音訊原則時所遵循的基本程式，進行這些替換：</span><span class="sxs-lookup"><span data-stu-id="f1368-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="f1368-164">使用不同（且唯一的）原則名稱（例如商務用**Skype Server 影片**）。</span><span class="sxs-lookup"><span data-stu-id="f1368-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="f1368-165">將 DSCP 值設為**34** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="f1368-165">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="f1368-166">（請注意，您不需要使用34的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="f1368-166">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="f1368-167">唯一的需求是，您針對影片使用的 DSCP 值與音訊所用的不同。</span><span class="sxs-lookup"><span data-stu-id="f1368-167">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="f1368-168">使用先前設定的影片流量埠範圍。</span><span class="sxs-lookup"><span data-stu-id="f1368-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="f1368-169">例如，如果您已將埠57501到65535的備用，請將埠範圍設定為： **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="f1368-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="f1368-170">同樣地，應該將它設定為目的地埠範圍。</span><span class="sxs-lookup"><span data-stu-id="f1368-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="f1368-171">如果您決定建立用來管理應用程式共用流量的原則，您必須建立第三個原則，以進行下列替換：</span><span class="sxs-lookup"><span data-stu-id="f1368-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="f1368-172">使用不同（且唯一的）原則名稱（例如，**商務用 Skype Server 應用程式共用**）。</span><span class="sxs-lookup"><span data-stu-id="f1368-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="f1368-173">將 DSCP 值設為**24** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="f1368-173">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="f1368-174">（同樣地，您不需要使用 DSCP 值24。</span><span class="sxs-lookup"><span data-stu-id="f1368-174">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="f1368-175">唯一的需求是，您針對與音訊或影片搭配使用的應用程式共用，使用不同的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="f1368-175">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="f1368-176">使用先前設定的影片流量埠範圍。</span><span class="sxs-lookup"><span data-stu-id="f1368-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="f1368-177">例如，如果您已在應用程式共用中保留埠40803到49151，請將埠範圍設定為： **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="f1368-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="f1368-178">您所建立的新原則必須在您的 Edge 伺服器上刷新群組原則之後，才會生效。</span><span class="sxs-lookup"><span data-stu-id="f1368-178">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="f1368-179">雖然群組原則會定期自行進行重新整理，但是您可以在需要重新整理群組原則的每一台電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="f1368-179">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="f1368-180">此命令可以從商務用 Skype 伺服器內執行，或是從任何在 [管理員認證] 下執行的命令視窗中執行。</span><span class="sxs-lookup"><span data-stu-id="f1368-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="f1368-181">若要在 [管理員認證] 下執行命令視窗，請按一下 [**開始**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="f1368-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="f1368-182">請注意，即使執行 Gpudate 之後，您可能還需要重新開機 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1368-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="f1368-183">若要協助確保網路資料包是以適當的 DSCP 值標示，您也應該透過完成下列程式，在每個電腦上建立新的登錄專案：</span><span class="sxs-lookup"><span data-stu-id="f1368-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="f1368-184">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="f1368-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="f1368-185">在 [**執行**] 對話方塊中，輸入**regedit**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="f1368-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="f1368-186">在 [登錄編輯程式] 中，展開 [ **HKEY\_本機\_電腦**]，展開 [**系統**]、[ **CurrentControlSet**]、[**服務**]，然後再展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="f1368-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="f1368-187">以滑鼠右鍵按一下 [ **Tcpip**]，指向 [**新增**]，然後按一下 [**金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="f1368-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="f1368-188">建立新的登錄金鑰之後，請輸入**QoS**，然後按 enter 來重新命名金鑰。</span><span class="sxs-lookup"><span data-stu-id="f1368-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="f1368-189">以滑鼠右鍵按一下 [ **QoS**]，指向 [**新增**]，然後按一下 [**字串值**]。</span><span class="sxs-lookup"><span data-stu-id="f1368-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="f1368-190">建立新的登錄值之後，請輸入 [**不使用 NLA**]，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="f1368-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="f1368-191">按兩下 [**不使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="f1368-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="f1368-192">在 [**編輯字串**] 對話方塊中，于 [**值資料**] 方塊中輸入**1** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f1368-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="f1368-193">關閉 [登錄編輯程式]，然後重新開機您的電腦。</span><span class="sxs-lookup"><span data-stu-id="f1368-193">Close the Registry Editor and reboot your computer.</span></span>
