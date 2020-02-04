---
title: Lync Server 2013：針對會議、應用程式及中繼伺服器設定服務品質原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 385530e45c208ced2cce4815d1f60e596c2a08b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="684ee-102">在 Lync Server 2013 中針對會議、應用程式及中繼伺服器設定服務品質原則</span><span class="sxs-lookup"><span data-stu-id="684ee-102">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="684ee-103">_**主題上次修改日期：** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="684ee-103">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="684ee-104">設定埠範圍的方法是確保指定類型的所有流量（例如，所有音訊流量）都經過同一個埠組，以協助使用服務品質。</span><span class="sxs-lookup"><span data-stu-id="684ee-104">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports.</span></span> <span data-ttu-id="684ee-105">這可讓系統輕鬆識別並標示指定的資料包：如果埠49152是為音訊流量保留，則透過埠49152傳送的任何資料包都可以使用 DSCP 代碼來標示，以表示這是音訊包。</span><span class="sxs-lookup"><span data-stu-id="684ee-105">This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet.</span></span> <span data-ttu-id="684ee-106">接著，這可讓路由器將資料包識別為音訊資料包，並提供比未標記的資料包更高的優先順序（例如，用來將檔案從一個伺服器複製到另一個伺服器的資料包）。</span><span class="sxs-lookup"><span data-stu-id="684ee-106">In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="684ee-107">不過，只要將一組埠限制為特定類型的通信量，就不會導致資料包透過這些埠以適當的 DSCP 代碼標示。</span><span class="sxs-lookup"><span data-stu-id="684ee-107">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="684ee-108">除了定義埠範圍之外，您還必須建立服務原則，以指定要與每個埠範圍相關聯的 DSCP 代碼。</span><span class="sxs-lookup"><span data-stu-id="684ee-108">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="684ee-109">針對 Microsoft Lync Server 2013，通常代表建立兩個原則：一個用於音訊，另一個用於影片。</span><span class="sxs-lookup"><span data-stu-id="684ee-109">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="684ee-110">您可以使用群組原則輕鬆建立和管理服務品質原則。</span><span class="sxs-lookup"><span data-stu-id="684ee-110">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="684ee-111">（您也可以使用本機安全性原則來建立這些相同的原則。</span><span class="sxs-lookup"><span data-stu-id="684ee-111">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="684ee-112">不過，這需要您在每個電腦上重複相同的程式。您最初的 QoS 原則集（一個 for 音訊，另一個用於影片）應該只會套用到執行會議服務器、應用程式伺服器和/或中繼伺服器服務的 Lync Server 電腦。</span><span class="sxs-lookup"><span data-stu-id="684ee-112">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="684ee-113">如果所有這些電腦都位於同一個 Active Directory OU 中，您可以直接將新的群組原則物件（GPO）指派給該 OU。</span><span class="sxs-lookup"><span data-stu-id="684ee-113">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="684ee-114">或者，您也可以採取其他步驟，將新原則的目標設定為指定的電腦;例如，您可以將適當的電腦放在安全群組中，然後使用群組原則安全性篩選，將 GPO 只套用到該安全性群組。</span><span class="sxs-lookup"><span data-stu-id="684ee-114">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="684ee-115">若要建立用來管理音訊的服務品質原則，請登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="684ee-115">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="684ee-116">開啟 [群組原則管理] （按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**群組原則管理**]），然後完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="684ee-116">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="684ee-117">在 [群組原則管理] 中，找出要建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="684ee-117">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="684ee-118">例如，如果您所有的 Lync Server 電腦都位於名為 Lync Server 的 OU 中，則應該在 Lync Server OU 中建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="684ee-118">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="684ee-119">以滑鼠右鍵按一下適當的容器，然後按一下 [**在這個網域中建立 GPO]，然後在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="684ee-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="684ee-120">在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中，輸入新群組原則物件的名稱（例如**Lync Server QoS**），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="684ee-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="684ee-121">以滑鼠右鍵按一下新建立的原則，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="684ee-121">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="684ee-122">在 [群組原則管理編輯器] 中，展開 [**電腦**設定]，展開 [**原則**]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [**原則式 QoS**]，然後按一下 [**建立新策略**]。</span><span class="sxs-lookup"><span data-stu-id="684ee-122">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="684ee-123">在 [**原則式 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱（例如**Lync Server QoS**）。</span><span class="sxs-lookup"><span data-stu-id="684ee-123">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="684ee-124">選取 [**指定 DSCP 值**]，然後將值設定為**46**。</span><span class="sxs-lookup"><span data-stu-id="684ee-124">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="684ee-125">[離開]**指定輸出限制率**未選取，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="684ee-125">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="684ee-126">在下一頁上，確認已選取 [**所有應用程式**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="684ee-126">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="684ee-127">這只會確保所有應用程式都能將來自指定埠範圍的資料包與指定的 DSCP 代碼相符。</span><span class="sxs-lookup"><span data-stu-id="684ee-127">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="684ee-128">在第三個頁面上，確認已選取 [**所有來源 ip 位址] 和 [任何目的地 ip 位址**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="684ee-128">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="684ee-129">這兩項設定可確保無論哪些電腦（IP 位址）傳送這些資料包，以及哪些電腦（IP 位址）會接收那些資料包，都會管理資料包。</span><span class="sxs-lookup"><span data-stu-id="684ee-129">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="684ee-130">在第4頁，從 [**選取此 QoS 原則適用**于] 下拉式清單中選取 [ **TCP 和 UDP** ]。</span><span class="sxs-lookup"><span data-stu-id="684ee-130">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="684ee-131">TCP （傳輸控制通訊協定）和 UDP （使用者資料包通訊協定）是 Lync Server 及其用戶端應用程式最常使用的兩種網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="684ee-131">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="684ee-132">在 [標題] 底下，**指定來源埠號**，選取 [**從此來源埠或範圍**]。</span><span class="sxs-lookup"><span data-stu-id="684ee-132">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="684ee-133">在隨附的文字方塊中，輸入為音訊廣播保留的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="684ee-133">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="684ee-134">例如，如果您是透過埠57500將埠49152預留給音訊流量，請輸入使用此格式的埠範圍： **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="684ee-134">For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="684ee-135">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="684ee-135">Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="684ee-136">46的 DSCP 值有點隨意：雖然 DSCP 46 通常是用來標示音訊資料包，但您不需要使用 DSCP 46 進行音訊通訊。</span><span class="sxs-lookup"><span data-stu-id="684ee-136">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="684ee-137">如果您已經實現 QoS，且您使用的是不同的音訊 DSCP 代碼（例如，DSCP 40），那麼您應該設定您的服務品質原則，以使用相同的程式碼（亦即，40的音訊）。</span><span class="sxs-lookup"><span data-stu-id="684ee-137">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="684ee-138">如果您只是在執行服務品質，建議您將 DSCP 46 用於音訊，只要這個值通常是用來標示音訊資料包就好了。</span><span class="sxs-lookup"><span data-stu-id="684ee-138">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="684ee-139">在您建立音訊流量的 QoS 原則之後，您應該接著建立影片流量的第二個原則（也就是第三個管理應用程式共用流量的原則）。</span><span class="sxs-lookup"><span data-stu-id="684ee-139">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="684ee-140">若要建立影片的原則，請遵循您在建立音訊原則時所遵循的基本程式，進行這些替換：</span><span class="sxs-lookup"><span data-stu-id="684ee-140">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="684ee-141">使用不同（且唯一的）原則名稱（例如**Lync Server Video**）。</span><span class="sxs-lookup"><span data-stu-id="684ee-141">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="684ee-142">將 DSCP 值設為**34** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="684ee-142">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="684ee-143">（請注意，您不需要使用34的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="684ee-143">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="684ee-144">唯一的需求是，您針對影片使用的 DSCP 值與音訊所用的不同。</span><span class="sxs-lookup"><span data-stu-id="684ee-144">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="684ee-145">針對影片流量，請使用先前設定的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="684ee-145">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="684ee-146">例如，如果您已將埠57501到65535，然後將埠範圍設定為： **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="684ee-146">For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="684ee-147">如果您決定建立用來管理應用程式共用流量的原則，您必須建立第三個原則，進行下列替換：</span><span class="sxs-lookup"><span data-stu-id="684ee-147">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="684ee-148">使用不同（且唯一的）原則名稱（例如**Lync Server 應用程式共用**）。</span><span class="sxs-lookup"><span data-stu-id="684ee-148">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="684ee-149">將 DSCP 值設為**24** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="684ee-149">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="684ee-150">（同樣地，您不需要使用 DSCP 值24。</span><span class="sxs-lookup"><span data-stu-id="684ee-150">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="684ee-151">唯一的需求是，您針對與音訊或影片搭配使用的應用程式共用，使用不同的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="684ee-151">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="684ee-152">針對影片流量，請使用先前設定的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="684ee-152">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="684ee-153">例如，如果您已將埠40803到49151保留，以進行應用程式共用，請將埠範圍設定為： **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="684ee-153">For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="684ee-154">您所建立的新原則必須在您的 Lync Server 電腦上重新整理群組原則後才會生效。</span><span class="sxs-lookup"><span data-stu-id="684ee-154">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="684ee-155">雖然群組原則會定期自行進行重新整理，但是您可以在需要重新整理群組原則的每一台電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="684ee-155">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="684ee-156">此命令可以從 Lync Server 管理命令介面或在管理員認證下執行的任何命令視窗中執行。</span><span class="sxs-lookup"><span data-stu-id="684ee-156">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="684ee-157">若要在 [管理員認證] 下執行命令視窗，請按一下 [**開始**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="684ee-157">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="684ee-158">若要確認已套用新的 QoS 原則，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="684ee-158">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="684ee-159">在 Lync Server 電腦上，按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="684ee-159">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="684ee-160">在 [**執行**] 對話方塊中，輸入**regedit** ，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="684ee-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="684ee-161">在 [登錄編輯程式] 中，展開 [**電腦**]，展開 [ \*\* \_HKEY 本機\_電腦**]，展開 [**軟體**]，然後展開 [**原則**]、[ **Microsoft**]、[ **Windows**]，**然後按一下 [\*\*</span><span class="sxs-lookup"><span data-stu-id="684ee-161">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="684ee-162">在 [ **QoS** ] 底下，您應該會看到您剛建立的每一個 QoS 原則的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="684ee-162">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="684ee-163">例如，如果您已建立兩個新的原則（一個名為 Lync Server Audio QoS，還有另一個命名的 Lync 伺服器影片 QoS），您就應該有 Lync Server 音訊 QoS 和 Lync Server Video QoS 的註冊專案。</span><span class="sxs-lookup"><span data-stu-id="684ee-163">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="684ee-164">若要協助確保網路資料包是以適當的 DSCP 值標示，您也應該透過完成下列程式，在每個電腦上建立新的登錄專案：</span><span class="sxs-lookup"><span data-stu-id="684ee-164">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="684ee-165">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="684ee-165">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="684ee-166">在 [**執行**] 對話方塊中，輸入**regedit** ，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="684ee-166">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="684ee-167">在 [登錄編輯程式] 中，展開 [ **HKEY\_本機\_電腦**]，展開 [**系統**]、[ **CurrentControlSet**]、[**服務**]，然後再展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="684ee-167">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="684ee-168">以滑鼠右鍵按一下 [ **Tcpip**]，指向 [**新增**]，然後按一下 [**金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="684ee-168">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="684ee-169">建立新的登錄金鑰之後，請輸入**QoS** ，然後按 enter 來重新命名金鑰。</span><span class="sxs-lookup"><span data-stu-id="684ee-169">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="684ee-170">以滑鼠右鍵按一下 [ **QoS**]，指向 [**新增**]，然後按一下 [**字串值**]。</span><span class="sxs-lookup"><span data-stu-id="684ee-170">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="684ee-171">建立新的登錄值之後，請輸入 [**不要使用 NLA** ]，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="684ee-171">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="684ee-172">按兩下 [**不使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="684ee-172">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="684ee-173">在 [**編輯字串**] 對話方塊中，于 [**值資料**] 方塊中輸入**1** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="684ee-173">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="684ee-174">關閉 [登錄編輯程式]，然後重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="684ee-174">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

