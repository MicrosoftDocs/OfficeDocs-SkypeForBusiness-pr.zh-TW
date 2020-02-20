---
title: Lync Server 2013： 設定您的會議、 應用程式及中繼伺服器的服務品質原則
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
ms.openlocfilehash: 4711c618669a8fe47a877b4adeafe7759564855f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="a999e-102">在 Lync Server 2013 中設定服務品質原則會議、 應用程式及中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="a999e-102">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a999e-103">_**上次修改主題：** 2014年-06-23_</span><span class="sxs-lookup"><span data-stu-id="a999e-103">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="a999e-104">設定連接埠範圍來確保指定的類型 （例如，所有音訊流量） 的所有流量都通過的同一個連接埠設定有助於品質的服務使用。</span><span class="sxs-lookup"><span data-stu-id="a999e-104">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports.</span></span> <span data-ttu-id="a999e-105">這可以方便識別，並將標示為指定的封包系統： 如果 49152 它保留給音訊的流量，然後透過連接埠 49152 出差任何封包都可以使用表示這是音訊封包的 DSCP 代碼標記。</span><span class="sxs-lookup"><span data-stu-id="a999e-105">This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet.</span></span> <span data-ttu-id="a999e-106">接著，這可讓路由器，以識別為音訊封包的封包，並提供更高的優先順序，比未標示的封包 （例如用於檔案複製到另一部伺服器的封包）。</span><span class="sxs-lookup"><span data-stu-id="a999e-106">In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="a999e-107">不過，只要限制特定類型流量的連接埠的一組不會導致封包標示適當的 DSCP 程式碼這些連接埠透過。</span><span class="sxs-lookup"><span data-stu-id="a999e-107">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="a999e-108">除了定義連接埠範圍，您也必須建立的服務品質原則，指定要與每個連接埠範圍相關聯的 DSCP 程式碼。</span><span class="sxs-lookup"><span data-stu-id="a999e-108">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="a999e-109">針對 Microsoft Lync Server 2013，通常也就是說，建立兩個原則： 一個用於音訊和視訊，以利。</span><span class="sxs-lookup"><span data-stu-id="a999e-109">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="a999e-110">服務品質原則是大部分輕鬆地建立，並管理，使用群組原則。</span><span class="sxs-lookup"><span data-stu-id="a999e-110">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="a999e-111">（這些相同的原則也可以建立使用本機安全性原則。</span><span class="sxs-lookup"><span data-stu-id="a999e-111">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="a999e-112">不過，會要求您重複相同的程序，在每一台電腦上。）QoS 原則 （一個用於音訊） 和影片，以利您初始設定應該是只套用至 Lync Server 電腦執行的會議伺服器、 應用程式伺服器及/或中繼伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="a999e-112">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="a999e-113">如果所有的這些電腦都位於相同的 Active Directory OU 然後您可以直接指派新的群組原則物件 (GPO) 到該 OU。</span><span class="sxs-lookup"><span data-stu-id="a999e-113">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="a999e-114">或者，您可以執行下列其他步驟以將目標設至指定的電腦; 新的原則例如，您可以將適當的電腦放在 [安全性] 群組中，然後使用群組原則安全性篩選器套用到 GPO 專為該 [安全性] 群組。</span><span class="sxs-lookup"><span data-stu-id="a999e-114">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="a999e-115">若要建立的服務品質原則來管理音訊，請登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="a999e-115">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="a999e-116">開啟群組原則管理] （按一下 [**開始]**、 指向 [**系統管理工具**]，然後按一下 [**群組原則管理**），然後完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="a999e-116">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="a999e-p105">在群組原則管理中，找出要用來建立新原則的容器。例如，如果您的所有 Lync Server 電腦都位在名為 Lync Server 的 OU 中，則新原則應建立在 Lync Server OU 中。</span><span class="sxs-lookup"><span data-stu-id="a999e-p105">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="a999e-119">以滑鼠右鍵按一下適當的容器，然後按一下 [在這個網域中建立 GPO 並連結到]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a999e-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="a999e-120">在 [**新增 GPO** ] 對話方塊中，(例如， **Lync Server QoS**) 上的 [**名稱**] 方塊中輸入新的群組原則物件的名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a999e-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="a999e-121">以滑鼠右鍵按一下新建的原則 ，然後按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a999e-121">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="a999e-122">在群組原則管理編輯器 」 中，展開 [**電腦組態**]、 展開 [**原則**]、 展開 [ **Windows 設定**，以滑鼠右鍵按一下 [**原則式 QoS**]，，然後按一下 [**建立新原則**。</span><span class="sxs-lookup"><span data-stu-id="a999e-122">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="a999e-123">在 [**原則式 QoS** ] 對話方塊中，在 [開啟] 頁面中，輸入 [**名稱**] 方塊中的新原則 (例如， **Lync Server QoS**) 的名稱。</span><span class="sxs-lookup"><span data-stu-id="a999e-123">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="a999e-124">選取 [指定 DSCP 數值]\*\*\*\*，並將該值設為 **46**。</span><span class="sxs-lookup"><span data-stu-id="a999e-124">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="a999e-125">將 [指定輸出節流閥速率]\*\*\*\* 保留未選取狀態，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a999e-125">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="a999e-126">在下一頁上，確定已選取 [所有應用程式]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a999e-126">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="a999e-127">這只是可確保所有應用程式會比對從指定的連接埠範圍與指定的 DSCP 程式碼的封包。</span><span class="sxs-lookup"><span data-stu-id="a999e-127">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="a999e-128">在第三個頁面上，確定這兩個**任何來源 IP 位址和任何目的地 IP 位址**已選取，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a999e-128">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="a999e-129">這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。</span><span class="sxs-lookup"><span data-stu-id="a999e-129">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="a999e-130">在第四頁上，從 [選取此 QoS 原則套用的通訊協定]\*\*\*\* 下拉式清單中選取 [TCP 及 UDP]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a999e-130">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="a999e-131">（傳輸控制通訊協定） TCP 及 UDP （使用者資料包通訊協定） 是最常使用的 Lync Server 和其用戶端應用程式的兩個網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="a999e-131">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="a999e-132">在**指定的來源連接埠號碼**標題下，選取 [**從這個來源的連接埠或範圍**。</span><span class="sxs-lookup"><span data-stu-id="a999e-132">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="a999e-133">在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="a999e-133">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="a999e-134">例如，如果您已保留連接埠 49152 透過連接埠 57500 的音訊流量進入使用這種格式的連接埠範圍： **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="a999e-134">For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="a999e-135">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a999e-135">Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a999e-136">46 的 DSCP 值是有點任意： 雖然 DSCP 46 通常用於標示音訊封包，您不必使用 DSCP 46 音訊通訊。</span><span class="sxs-lookup"><span data-stu-id="a999e-136">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="a999e-137">如果您已執行 QoS，而您使用不同的 DSCP 程式碼之音訊 (例如，DSCP 40)，您應該設定您的服務品質原則，以使用相同的程式碼 (亦即，之音訊的 40)。</span><span class="sxs-lookup"><span data-stu-id="a999e-137">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="a999e-138">如果您只是現在要實作的服務品質，則建議您使用 DSCP 46 音訊，只是因為該值通常用來標記音訊封包。</span><span class="sxs-lookup"><span data-stu-id="a999e-138">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="a999e-139">當您建立音訊流量的 QoS 原則之後您再應該建立視訊流量 （並選擇性地管理應用程式共用流量的第三個原則） 的第二個原則。</span><span class="sxs-lookup"><span data-stu-id="a999e-139">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="a999e-140">若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：</span><span class="sxs-lookup"><span data-stu-id="a999e-140">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="a999e-141">使用不同的 (且唯一的) 原則名稱 (例如，**Lync Server Video**)。</span><span class="sxs-lookup"><span data-stu-id="a999e-141">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="a999e-p113">將 DSCP 值設為 **34** 而不是 46。(請注意，DSCP 值不一定要使用 34。唯一的要求是用於視訊和音訊的 DSCP 值必須不同。)</span><span class="sxs-lookup"><span data-stu-id="a999e-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="a999e-145">為視訊傳輸使用先前設定的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="a999e-145">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="a999e-146">例如，如果您已為視訊保留連接埠 57501 到 65535，則將連接埠範圍設為：**57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="a999e-146">For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="a999e-147">如果您決定建立原則來管理應用程式共用流量，則必須建立第三原則，請替換下列項目：</span><span class="sxs-lookup"><span data-stu-id="a999e-147">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="a999e-148">使用不同的 (且唯一的) 原則名稱 (例如，**Lync Server Application Sharing**)。</span><span class="sxs-lookup"><span data-stu-id="a999e-148">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="a999e-p115">將 DSCP 值設為 **24** 而不是 46。(再強調一次，DSCP 值不一定要使用 24。唯一的要求是用於應用程式共用的 DSCP 值必須與視訊或音訊不同。)</span><span class="sxs-lookup"><span data-stu-id="a999e-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="a999e-p116">為視訊傳輸使用先前設定的連接埠範圍。例如，如果您已為應用程式共用保留連接埠 40803 到 49151，則將連接埠範圍設為：**40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="a999e-p116">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="a999e-154">您已建立的新原則不會生效之前已重新整理 Lync Server 的電腦上的群組原則。</span><span class="sxs-lookup"><span data-stu-id="a999e-154">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="a999e-155">雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="a999e-155">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="a999e-156">可以從執行此命令，或從系統管理員認證執行任何命令視窗中 [Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="a999e-156">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="a999e-157">若要以系統管理員憑證執行命令視窗，請按一下 [開始]\*\*\*\*，以滑鼠右鍵按一下 [命令提示字元]\*\*\*\*，然後按一下 [以系統管理員身分執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a999e-157">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="a999e-158">若要確認已套用新的 QoS 原則，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a999e-158">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="a999e-159">Lync Server 的電腦上，按一下 [**開始]** ，然後按一下 [**執行**。</span><span class="sxs-lookup"><span data-stu-id="a999e-159">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="a999e-160">在 [執行]\*\*\*\* 對話方塊中，輸入 **regedit**，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="a999e-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="a999e-161">在 「 登錄編輯程式中，展開 [**電腦**]，依序展開 [ **HKEY\_本機\_機器**、 展開**軟體**、 展開 [**原則**]，依序展開 [ **Microsoft**、 **Windows**中，依序展開，然後按一下**QoS**。</span><span class="sxs-lookup"><span data-stu-id="a999e-161">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="a999e-162">[ **QoS**您應該為每個您剛才建立的 QoS 原則會看到登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="a999e-162">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="a999e-163">例如，如果您建立兩個新的原則 （一個具名的 Lync Server 音訊 QoS 和其他具名的 Lync Server 視訊 QoS） 請 Lync Server 音訊 QoS 和 Lync Server 視訊 QoS 應該登錄項目。</span><span class="sxs-lookup"><span data-stu-id="a999e-163">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="a999e-164">為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="a999e-164">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="a999e-165">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a999e-165">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="a999e-166">在 [執行]\*\*\*\* 對話方塊中，輸入 **regedit**，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="a999e-166">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="a999e-167">在登錄編輯程式中，依序展開 [ **HKEY\_本機\_機器**、 展開 [**系統**、 [ **CurrentControlSet**、 展開 [**服務**] 及 [ **tcpip]**。</span><span class="sxs-lookup"><span data-stu-id="a999e-167">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="a999e-p120">以滑鼠右鍵按一下 [Tcpip]\*\*\*\*，指向 [新增]\*\*\*\*，然後按一下 [索引鍵]\*\*\*\*。建立新的登錄機碼之後，輸入 **QoS**，然後按 ENTER 鍵，以將索引鍵重新命名。</span><span class="sxs-lookup"><span data-stu-id="a999e-p120">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="a999e-p121">以滑鼠右鍵按一下 [QoS]\*\*\*\*，指向 [新增]\*\*\*\*，然後按一下 [字串值]\*\*\*\*。建立新的登錄值之後，輸入 **Do not use NLA**，然後按 ENTER 鍵，以將該值重新命名。</span><span class="sxs-lookup"><span data-stu-id="a999e-p121">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="a999e-172">連按兩下 [**不使用 NLA**。</span><span class="sxs-lookup"><span data-stu-id="a999e-172">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="a999e-173">在 [編輯字串]\*\*\*\* 對話方塊的 [數值資料]\*\*\*\* 方塊中輸入 **1**，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a999e-173">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="a999e-174">關閉登錄編輯程式，然後重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="a999e-174">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

