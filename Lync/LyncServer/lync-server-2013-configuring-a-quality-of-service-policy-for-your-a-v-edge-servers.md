---
title: 為您的 A/V 邊緣伺服器設定品質原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f5bfabfe794ed274d28074aaf162bc715a6ed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="2deb9-102">在 Lync Server 2013 中設定您的 A/V 邊緣伺服器的服務品質原則</span><span class="sxs-lookup"><span data-stu-id="2deb9-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2deb9-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2deb9-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2deb9-104">除了為您的會議、應用程式和中繼伺服器建立 QoS 原則之外，您還必須為 A/V 邊緣伺服器的內部端建立音訊與影片原則。</span><span class="sxs-lookup"><span data-stu-id="2deb9-104">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="2deb9-105">不過，在 Edge 伺服器上使用的原則與在您的會議、應用程式和中繼伺服器上使用的原則不同。</span><span class="sxs-lookup"><span data-stu-id="2deb9-105">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="2deb9-106">針對會議、應用程式及中繼伺服器，您指定的來源埠範圍為有了 Edge 伺服器，您必須指定目的地埠範圍。</span><span class="sxs-lookup"><span data-stu-id="2deb9-106">For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="2deb9-107">因為您無法直接將會議、應用程式和中繼伺服器 QoS 原則套用至 Edge 伺服器：這些原則根本無法運作。</span><span class="sxs-lookup"><span data-stu-id="2deb9-107">Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="2deb9-108">相反地，您必須建立新的原則，並將這些原則只套用到 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="2deb9-108">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="2deb9-109">下列程式說明建立 Active Directory 群組原則物件的程式，這些物件可用於管理 Edge 伺服器上的服務品質。</span><span class="sxs-lookup"><span data-stu-id="2deb9-109">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="2deb9-110">當然，您的邊緣伺服器可能是不具備 Active Directory 帳戶的獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="2deb9-110">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="2deb9-111">如果是這種情況，您可以使用本機組策略，而不是 Active Directory 群組原則：唯一的差別是，您必須使用本機組策略編輯器來建立這些本機原則，而且必須在每個 Edge 伺服器上分別建立相同的原則組。</span><span class="sxs-lookup"><span data-stu-id="2deb9-111">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="2deb9-112">若要在 Edge 伺服器上啟動本機組策略編輯器，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2deb9-112">To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="2deb9-113">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="2deb9-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="2deb9-114">在 [**執行**] 對話方塊中，輸入 [ **gpedit.msc** ]，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="2deb9-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="2deb9-115">如果您要建立 Active Directory 的原則，您應該登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="2deb9-115">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="2deb9-116">在這種情況下，請開啟 [群組原則管理] （按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**群組原則管理**]），然後完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2deb9-116">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="2deb9-117">在 [群組原則管理] 中，找出要建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="2deb9-117">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="2deb9-118">例如，如果您所有的 Lync Server 電腦都位於名為 Lync Server 的 OU 中，則應該在 Lync Server OU 中建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="2deb9-118">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="2deb9-119">以滑鼠右鍵按一下適當的容器，然後按一下 [**在這個網域中建立 GPO]，然後在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="2deb9-120">在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中，輸入新群組原則物件的名稱（例如**Lync Server 音訊**），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="2deb9-121">以滑鼠右鍵按一下新建立的原則，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2deb9-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="2deb9-122">無論您是建立 Active Directory 原則或本機原則，此程式都是相同的：</span><span class="sxs-lookup"><span data-stu-id="2deb9-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="2deb9-123">在 [群組原則管理編輯器] 或 [本機組策略編輯器] 中，展開 [**電腦**設定]，展開 [**原則**]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [**原則式 QoS**]，然後按一下 [**建立新策略**]。</span><span class="sxs-lookup"><span data-stu-id="2deb9-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="2deb9-124">在 [**原則式 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱（例如**Lync Server Audio**）。</span><span class="sxs-lookup"><span data-stu-id="2deb9-124">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="2deb9-125">選取 [**指定 DSCP 值**]，然後將值設定為**46**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-125">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="2deb9-126">[離開]**指定輸出限制率**未選取，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-126">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="2deb9-127">在下一頁上，確認已選取 [**所有應用程式**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-127">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="2deb9-128">此設定會指示網路尋找 DSCP 標記為46的所有資料包，而不只是特定應用程式所建立的資料包。</span><span class="sxs-lookup"><span data-stu-id="2deb9-128">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="2deb9-129">在第三個頁面上，確認已選取 [**所有來源 ip 位址**] 和 [**任何目的地 ip 位址**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-129">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="2deb9-130">這兩項設定可確保無論哪些電腦（IP 位址）傳送這些資料包，以及哪些電腦（IP 位址）會接收那些資料包，都會管理資料包。</span><span class="sxs-lookup"><span data-stu-id="2deb9-130">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="2deb9-131">在第4頁，從 [**選取此 QoS 原則適用**于] 下拉式清單中選取 [ **TCP 和 UDP** ]。</span><span class="sxs-lookup"><span data-stu-id="2deb9-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="2deb9-132">TCP （傳輸控制通訊協定）和 UDP （使用者資料包通訊協定）是 Lync Server 及其用戶端應用程式最常使用的兩種網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="2deb9-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="2deb9-133">在 [標題] 底下**指定目的地埠號**，選取 [**從此目的地埠或範圍**]。</span><span class="sxs-lookup"><span data-stu-id="2deb9-133">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="2deb9-134">在隨附的文字方塊中，輸入為音訊廣播保留的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="2deb9-134">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="2deb9-135">例如，如果您是透過埠57500將埠49152預留給音訊流量，請輸入使用此格式的埠範圍： **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-135">For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="2deb9-136">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-136">Click **Finish**.</span></span>

<span data-ttu-id="2deb9-137">在您建立音訊流量的 QoS 原則之後，您應該為影片流量建立第二個原則。</span><span class="sxs-lookup"><span data-stu-id="2deb9-137">After you have created the QoS policy for audio traffic you should create a second policy for video traffic.</span></span> <span data-ttu-id="2deb9-138">若要建立影片的原則，請遵循您在建立音訊原則時所遵循的基本程式，進行這些替換：</span><span class="sxs-lookup"><span data-stu-id="2deb9-138">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="2deb9-139">使用不同（且唯一的）原則名稱（例如**Lync Server Video**）。</span><span class="sxs-lookup"><span data-stu-id="2deb9-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="2deb9-140">將 DSCP 值設為**34** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="2deb9-140">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="2deb9-141">（請注意，您不需要使用34的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="2deb9-141">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="2deb9-142">唯一的需求是，您針對影片使用的 DSCP 值與音訊所用的不同。</span><span class="sxs-lookup"><span data-stu-id="2deb9-142">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="2deb9-143">針對影片流量，請使用先前設定的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="2deb9-143">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="2deb9-144">例如，如果您已將埠57501到65535，然後將埠範圍設定為： **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-144">For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="2deb9-145">同樣地，應該將它設定為目的地埠範圍。</span><span class="sxs-lookup"><span data-stu-id="2deb9-145">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="2deb9-146">如果您決定建立用來管理應用程式共用流量的原則，您必須建立第三個原則，進行下列替換：</span><span class="sxs-lookup"><span data-stu-id="2deb9-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="2deb9-147">使用不同（且唯一的）原則名稱（例如**Lync Server 應用程式共用**）。</span><span class="sxs-lookup"><span data-stu-id="2deb9-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="2deb9-148">將 DSCP 值設為**24** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="2deb9-148">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="2deb9-149">（同樣地，您不需要使用 DSCP 值24。</span><span class="sxs-lookup"><span data-stu-id="2deb9-149">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="2deb9-150">唯一的需求是，您針對與音訊或影片搭配使用的應用程式共用，使用不同的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="2deb9-150">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="2deb9-151">針對影片流量，請使用先前設定的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="2deb9-151">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="2deb9-152">例如，如果您已將埠40803到49151保留，以進行應用程式共用，請將埠範圍設定為： **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-152">For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="2deb9-153">您所建立的新原則必須在您的 Edge 伺服器上刷新群組原則之後，才會生效。</span><span class="sxs-lookup"><span data-stu-id="2deb9-153">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="2deb9-154">雖然群組原則會定期自行進行重新整理，但是您可以在需要重新整理群組原則的每一台電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="2deb9-154">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="2deb9-155">這個命令可以從 Lync 伺服器內執行，或從任何在系統管理員認證的命令視窗中執行。</span><span class="sxs-lookup"><span data-stu-id="2deb9-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="2deb9-156">若要在 [管理員認證] 下執行命令視窗，請按一下 [**開始**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="2deb9-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="2deb9-157">請注意，即使執行 Gpudate 之後，您可能還需要重新開機 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="2deb9-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="2deb9-158">若要協助確保網路資料包是以適當的 DSCP 值標示，您也應該透過完成下列程式，在每個電腦上建立新的登錄專案：</span><span class="sxs-lookup"><span data-stu-id="2deb9-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="2deb9-159">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="2deb9-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="2deb9-160">在 [**執行**] 對話方塊中，輸入**regedit** ，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="2deb9-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="2deb9-161">在 [登錄編輯程式] 中，展開 [ **HKEY\_本機\_電腦**]，展開 [**系統**]、[ **CurrentControlSet**]、[**服務**]，然後再展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="2deb9-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="2deb9-162">以滑鼠右鍵按一下 [ **Tcpip**]，指向 [**新增**]，然後按一下 [**金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="2deb9-162">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="2deb9-163">建立新的登錄金鑰之後，請輸入**QoS** ，然後按 enter 來重新命名金鑰。</span><span class="sxs-lookup"><span data-stu-id="2deb9-163">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="2deb9-164">以滑鼠右鍵按一下 [ **QoS**]，指向 [**新增**]，然後按一下 [**字串值**]。</span><span class="sxs-lookup"><span data-stu-id="2deb9-164">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="2deb9-165">建立新的登錄值之後，請輸入 [**不要使用 NLA** ]，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="2deb9-165">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="2deb9-166">按兩下 [**不使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="2deb9-166">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="2deb9-167">在 [**編輯字串**] 對話方塊中，于 [**值資料**] 方塊中輸入**1** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2deb9-167">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="2deb9-168">關閉 [登錄編輯程式]，然後重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="2deb9-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

