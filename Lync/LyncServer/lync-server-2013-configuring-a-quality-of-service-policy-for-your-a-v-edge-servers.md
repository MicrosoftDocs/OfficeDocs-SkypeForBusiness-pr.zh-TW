---
title: 設定服務品質原則的 A / V Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b75e6094fd7d84e086e31bbc4535faf0df84155
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="edd43-102">設定服務品質原則的 A / V Edge Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edd43-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edd43-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="edd43-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="edd43-p101">除了為會議伺服器、應用程式伺服器及中繼伺服器建立 QoS 原則，您也必須為 A/V Edge Server 的內部端建立音訊及視訊原則。不過，在 Edge Server 上使用的原則，不同於在會議伺服器、應用程式伺服器及中繼伺服器上使用的原則。針對會議伺服器、應用程式伺服器及中繼伺服器，您會指定來源連接埠範圍；針對 Edge Server，則需要指定目的連接埠範圍。因此，您不能直接將會議伺服器、應用程式伺服器及中繼伺服器 QoS 原則套用至 Edge Server：這些原則就是不會作用。反之，您必須建立新的原則，並將這些原則只套用到 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="edd43-p101">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers. However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers. For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range. Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work. Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="edd43-p102">下列程序說明如何在 Edge Server 上，建立可以用來管理服務品質的 Active Directory 群組原則物件。當然，您的 Edge Server 有可能是沒有 Active Directory 帳戶的獨立伺服器。若是如此，您可以使用本機群組原則來代替 Active Directory 群組原則：唯一不同的是，您必須使用本機群組原則編輯器來建立這些本機原則，而且必須在每部 Edge Server 上個別建立相同的原則集。若要在 Edge Server 上啟動本機群組原則編輯器，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="edd43-p102">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers. Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts. If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server. To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="edd43-113">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="edd43-114">在 [執行]\*\*\*\* 對話方塊中，輸入 **gpedit.msc**，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="edd43-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="edd43-p103">如果您要建立 Active Directory 型原則，應登入已安裝群組原則管理的電腦。之後，開啟群組原則管理 (按一下 [開始]\*\*\*\*，指向 [系統管理工具]\*\*\*\*，然後按一下 [群組原則管理]\*\*\*\*)，接著完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="edd43-p103">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed. In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="edd43-p104">在群組原則管理中，找出要用來建立新原則的容器。例如，如果您的所有 Lync Server 電腦都位在名為 Lync Server 的 OU 中，則新原則應建立在 Lync Server OU 中。</span><span class="sxs-lookup"><span data-stu-id="edd43-p104">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="edd43-119">以滑鼠右鍵按一下適當的容器，然後按一下 [在這個網域中建立 GPO 並連結到]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="edd43-120">在 [新增 GPO]\*\*\*\* 對話方塊的 [名稱]\*\*\*\* 方塊中，輸入新群組原則物件的名稱 (例如，**Lync Server Audio**) ，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="edd43-121">以滑鼠右鍵按一下新建的原則 ，然後按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="edd43-122">從這裡開始，無論您是要建立 Active Directory 原則或本機原則，程序都一樣：</span><span class="sxs-lookup"><span data-stu-id="edd43-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="edd43-123">在群組原則管理編輯器或本機群組原則編輯器中，依序展開 [電腦設定]\*\*\*\*、[原則]\*\*\*\*、[Windows 設定]\*\*\*\*，以滑鼠右鍵按一下 [以原則為依據的 QoS]\*\*\*\*，然後按一下 [建立新原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="edd43-p105">在 [以原則為依據的 QoS]\*\*\*\* 對話方塊中，於開啟頁面上的 [名稱]\*\*\*\* 方塊中輸入新原則的名稱 (例如，**Lync Server Audio**)。選取 [指定 DSCP 數值]\*\*\*\*，並將該值設為 **46**。將 [指定輸出節流閥速率]\*\*\*\* 保留未選取狀態，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-p105">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="edd43-p106">在下一頁上，確定已選取 [所有應用程式]\*\*\*\*，然後按 [下一步]\*\*\*\*。此設定會指示網路尋找 DSCP 標示為 46 的所有封包，而不只是特定應用程式建立的封包。</span><span class="sxs-lookup"><span data-stu-id="edd43-p106">On the next page, make sure that **All applications** is selected and then click **Next**. This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="edd43-p107">在第三頁上，確定 [任何來源 IP 位址]\*\*\*\* 及 [任何目的地 IP 位址]\*\*\*\* 都已選取，然後按 [下一步]\*\*\*\*。這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。</span><span class="sxs-lookup"><span data-stu-id="edd43-p107">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="edd43-131">在第四頁上，從 [選取此 QoS 原則套用的通訊協定]\*\*\*\* 下拉式清單中選取 [TCP 及 UDP]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="edd43-132">（傳輸控制通訊協定） TCP 及 UDP （使用者資料包通訊協定） 是最常使用的 Lync Server 和其用戶端應用程式的兩個網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="edd43-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="edd43-p109">在 [指定目的地連接埠號碼]\*\*\*\* 標題底下，選取 [從此目的地連接埠或範圍]\*\*\*\*。在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。例如，如果您為音訊傳輸保留連接埠 49152 到 57500，則使用下列格式來輸入連接埠範圍：**49152:57500**。按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-p109">Under the heading **Specify the destination port number**, select **From this destination port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<span data-ttu-id="edd43-p110">在為音訊傳輸建立 QoS 原則之後，應為視訊傳輸建立第二個原則。若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：</span><span class="sxs-lookup"><span data-stu-id="edd43-p110">After you have created the QoS policy for audio traffic you should create a second policy for video traffic. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="edd43-139">使用不同的 (且唯一的) 原則名稱 (例如，**Lync Server Video**)。</span><span class="sxs-lookup"><span data-stu-id="edd43-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="edd43-p111">將 DSCP 值設為 **34** 而不是 46。(請注意，DSCP 值不一定要使用 34。唯一的要求是用於視訊和音訊的 DSCP 值必須不同。)</span><span class="sxs-lookup"><span data-stu-id="edd43-p111">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="edd43-p112">為視訊傳輸使用先前設定的連接埠範圍。例如，如果您已為視訊保留連接埠 57501 到 65535，則將連接埠範圍設為：**57501:65535**。再強調一次，這應該設為目的地連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="edd43-p112">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**. Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="edd43-146">如果您決定建立原則來管理應用程式共用流量，則必須建立第三原則，請替換下列項目：</span><span class="sxs-lookup"><span data-stu-id="edd43-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="edd43-147">使用不同的 (且唯一的) 原則名稱 (例如，**Lync Server Application Sharing**)。</span><span class="sxs-lookup"><span data-stu-id="edd43-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="edd43-p113">將 DSCP 值設為 **24** 而不是 46。(再強調一次，DSCP 值不一定要使用 24。唯一的要求是用於應用程式共用的 DSCP 值必須與視訊或音訊不同。)</span><span class="sxs-lookup"><span data-stu-id="edd43-p113">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="edd43-p114">為視訊傳輸使用先前設定的連接埠範圍。例如，如果您已為應用程式共用保留連接埠 40803 到 49151，則將連接埠範圍設為：**40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="edd43-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="edd43-p115">必須在 Edge Server 上重新整理群組原則之後，您建立的新原則才會生效。雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="edd43-p115">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="edd43-155">在 Lync Server 或從任何命令視窗中，執行系統管理員認證，可以從執行此命令。</span><span class="sxs-lookup"><span data-stu-id="edd43-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="edd43-156">若要以系統管理員憑證執行命令視窗，請按一下 [開始]\*\*\*\*，以滑鼠右鍵按一下 [命令提示字元]\*\*\*\*，然後按一下 [以系統管理員身分執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="edd43-157">請注意，即使在執行 Gpudate.exe 之後，可能還是需要重新啟動 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="edd43-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="edd43-158">為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="edd43-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="edd43-159">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="edd43-160">在 [執行]\*\*\*\* 對話方塊中，輸入 **regedit**，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="edd43-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="edd43-161">在登錄編輯程式中，依序展開 [ **HKEY\_本機\_機器**、 展開 [**系統**、 [ **CurrentControlSet**、 展開 [**服務**] 及 [ **tcpip]**。</span><span class="sxs-lookup"><span data-stu-id="edd43-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="edd43-p117">以滑鼠右鍵按一下 [Tcpip]\*\*\*\*，指向 [新增]\*\*\*\*，然後按一下 [索引鍵]\*\*\*\*。建立新的登錄機碼之後，輸入 **QoS**，然後按 ENTER 鍵，以將索引鍵重新命名。</span><span class="sxs-lookup"><span data-stu-id="edd43-p117">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="edd43-p118">以滑鼠右鍵按一下 [QoS]\*\*\*\*，指向 [新增]\*\*\*\*，然後按一下 [字串值]\*\*\*\*。建立新的登錄值之後，輸入 **Do not use NLA**，然後按 ENTER 鍵，以將該值重新命名。</span><span class="sxs-lookup"><span data-stu-id="edd43-p118">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="edd43-p119">按兩下 [Do not use NLA]\*\*\*\*。在 [編輯字串]\*\*\*\* 對話方塊的 [數值資料]\*\*\*\* 方塊中輸入 **1**，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="edd43-p119">Double-click **Do no use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="edd43-168">關閉登錄編輯程式，然後重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="edd43-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

