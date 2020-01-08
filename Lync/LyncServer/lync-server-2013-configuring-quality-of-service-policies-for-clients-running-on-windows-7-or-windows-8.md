---
title: Lync Server 2013：針對執行 Windows 7 或 Windows 8 的用戶端設定服務品質原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 365ce7a48a3c30a9e810d44edc1b7130ceb2643b
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "40976152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="75152-102">針對在 Windows 7 或 Windows 8 上執行的用戶端，在 Lync Server 2013 中設定服務品質原則</span><span class="sxs-lookup"><span data-stu-id="75152-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75152-103">_**主題上次修改日期：** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="75152-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="75152-104">除了指定要供 Lync 用戶端使用的埠範圍之外，您還必須建立要套用至用戶端電腦的個別服務品質。</span><span class="sxs-lookup"><span data-stu-id="75152-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="75152-105">（針對會議、應用程式和中繼伺服器所建立的服務品質原則，不應該套用到用戶端電腦。）此資訊僅適用于執行 Lync 2013 用戶端的電腦，以及 Windows 7 或 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="75152-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="75152-106">下列範例使用這組埠範圍來建立音訊原則和影片原則：</span><span class="sxs-lookup"><span data-stu-id="75152-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75152-107">用戶端流量類型</span><span class="sxs-lookup"><span data-stu-id="75152-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="75152-108">埠開始</span><span class="sxs-lookup"><span data-stu-id="75152-108">Port Start</span></span></th>
<th><span data-ttu-id="75152-109">埠範圍</span><span class="sxs-lookup"><span data-stu-id="75152-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75152-110">音訊</span><span class="sxs-lookup"><span data-stu-id="75152-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="75152-111">50020</span><span class="sxs-lookup"><span data-stu-id="75152-111">50020</span></span></p></td>
<td><p><span data-ttu-id="75152-112">20</span><span class="sxs-lookup"><span data-stu-id="75152-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75152-113">顯示器</span><span class="sxs-lookup"><span data-stu-id="75152-113">Video</span></span></p></td>
<td><p><span data-ttu-id="75152-114">58000</span><span class="sxs-lookup"><span data-stu-id="75152-114">58000</span></span></p></td>
<td><p><span data-ttu-id="75152-115">20</span><span class="sxs-lookup"><span data-stu-id="75152-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75152-116">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="75152-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="75152-117">42000</span><span class="sxs-lookup"><span data-stu-id="75152-117">42000</span></span></p></td>
<td><p><span data-ttu-id="75152-118">20</span><span class="sxs-lookup"><span data-stu-id="75152-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75152-119">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="75152-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="75152-120">42020</span><span class="sxs-lookup"><span data-stu-id="75152-120">42020</span></span></p></td>
<td><p><span data-ttu-id="75152-121">20</span><span class="sxs-lookup"><span data-stu-id="75152-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75152-122">若要建立適用于 Windows 7 或 Windows 8 電腦的服務品質音訊原則，請先登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="75152-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="75152-123">開啟 [群組原則管理] （按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**群組原則管理**]），然後完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="75152-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="75152-124">在 [群組原則管理] 中，找出要建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="75152-124">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="75152-125">例如，如果所有用戶端電腦都位於名為「用戶端」的 OU 中，則應該在用戶端 OU 中建立新原則。</span><span class="sxs-lookup"><span data-stu-id="75152-125">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="75152-126">以滑鼠右鍵按一下適當的容器，然後按一下 [**在這個網域中建立 GPO]，然後在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="75152-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="75152-127">在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中，輸入新群組原則物件的名稱（例如， **Lync 音訊**），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="75152-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="75152-128">以滑鼠右鍵按一下新建立的原則，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="75152-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="75152-129">在 [群組原則管理編輯器] 中，展開 [**電腦**設定]，展開 [**原則**]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [**原則式 QoS**]，然後按一下 [**建立新策略**]。</span><span class="sxs-lookup"><span data-stu-id="75152-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="75152-130">在 [**原則式 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱（例如**Lync 音訊**）。</span><span class="sxs-lookup"><span data-stu-id="75152-130">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="75152-131">選取 [**指定 DSCP 值**]，然後將值設定為**46**。</span><span class="sxs-lookup"><span data-stu-id="75152-131">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="75152-132">[離開]**指定輸出限制率**未選取，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="75152-132">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="75152-133">在下一頁中，選取 [**僅限具有此可執行檔名稱的應用程式**]，然後輸入名稱**Lync**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="75152-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="75152-134">這個設定會指示原則只將來自 Lync 用戶端的相符流量排定優先順序。</span><span class="sxs-lookup"><span data-stu-id="75152-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="75152-135">在第三個頁面上，確認已選取 [**所有來源 ip 位址**] 和 [**任何目的地 ip 位址**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="75152-135">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="75152-136">這兩項設定可確保無論哪些電腦（IP 位址）傳送這些資料包，以及哪些電腦（IP 位址）會接收那些資料包，都會管理資料包。</span><span class="sxs-lookup"><span data-stu-id="75152-136">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="75152-137">在第4頁，從 [**選取此 QoS 原則適用**于] 下拉式清單中選取 [ **TCP 和 UDP** ]。</span><span class="sxs-lookup"><span data-stu-id="75152-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="75152-138">TCP （傳輸控制通訊協定）和 UDP （使用者資料包通訊協定）是 Lync Server 及其用戶端應用程式最常使用的兩種網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="75152-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="75152-139">在 [標題] 底下，**指定來源埠號**，選取 [**從此來源埠或範圍**]。</span><span class="sxs-lookup"><span data-stu-id="75152-139">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="75152-140">在隨附的文字方塊中，輸入為音訊廣播保留的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="75152-140">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="75152-141">例如，如果您是透過埠50039將埠50020預留給音訊流量，請輸入使用此格式的埠範圍： **50020:50039**。</span><span class="sxs-lookup"><span data-stu-id="75152-141">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="75152-142">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="75152-142">Click **Finish**.</span></span>

<span data-ttu-id="75152-143">在您建立音訊的 QoS 原則之後，您應該先建立影片的第二個原則。</span><span class="sxs-lookup"><span data-stu-id="75152-143">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="75152-144">若要建立影片的原則，請遵循您在建立音訊原則時所遵循的基本程式，進行這些替換：</span><span class="sxs-lookup"><span data-stu-id="75152-144">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="75152-145">使用不同（且唯一的）原則名稱（例如**Lync 影片**）。</span><span class="sxs-lookup"><span data-stu-id="75152-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="75152-146">將 DSCP 值設為**34** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="75152-146">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="75152-147">（如前所述，您不需要使用 DSCP 值 34; 您只需指派不同于音訊所用的 DSCP 值即可）。</span><span class="sxs-lookup"><span data-stu-id="75152-147">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="75152-148">針對影片流量，請使用先前設定的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="75152-148">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="75152-149">例如，如果您已將埠58000到58019，然後將埠範圍設定為： **58000:58019**。</span><span class="sxs-lookup"><span data-stu-id="75152-149">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="75152-150">如果您決定建立用來管理應用程式共用流量的原則，請進行下列替換：</span><span class="sxs-lookup"><span data-stu-id="75152-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="75152-151">使用不同（且唯一的）原則名稱（例如**Lync Server 應用程式共用**）。</span><span class="sxs-lookup"><span data-stu-id="75152-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="75152-152">將 DSCP 值設為**24** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="75152-152">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="75152-153">（同樣地，此值不一定必須是 24; 它必須與用於音訊和影片的 DSCP 值不同）。</span><span class="sxs-lookup"><span data-stu-id="75152-153">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="75152-154">針對影片流量，請使用先前設定的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="75152-154">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="75152-155">例如，如果您已將埠42000到42019保留，以進行應用程式共用，請將埠範圍設定為： **42000:42019**。</span><span class="sxs-lookup"><span data-stu-id="75152-155">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="75152-156">針對檔案傳輸原則：</span><span class="sxs-lookup"><span data-stu-id="75152-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="75152-157">使用不同（且唯一的）原則名稱（例如， **Lync Server 檔案傳輸**）。</span><span class="sxs-lookup"><span data-stu-id="75152-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="75152-158">將 DSCP 值設為**14**。</span><span class="sxs-lookup"><span data-stu-id="75152-158">Set the DSCP value to **14**.</span></span> <span data-ttu-id="75152-159">（同樣地，這個值不一定是 14; 它必須是唯一的 DSCP 代碼。）</span><span class="sxs-lookup"><span data-stu-id="75152-159">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="75152-160">使用先前設定的應用程式埠範圍。</span><span class="sxs-lookup"><span data-stu-id="75152-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="75152-161">例如，如果您已將埠42020到42039保留，以進行應用程式共用，請將埠範圍設定為： **42020:42039**。</span><span class="sxs-lookup"><span data-stu-id="75152-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="75152-162">您所建立的新原則必須在用戶端電腦上重新整理群組原則後才會生效。</span><span class="sxs-lookup"><span data-stu-id="75152-162">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="75152-163">雖然群組原則會定期自行進行重新整理，但是您可以在需要重新整理群組原則的每一台電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="75152-163">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="75152-164">這個命令可以從任何執行在「管理員認證」的命令視窗中執行。</span><span class="sxs-lookup"><span data-stu-id="75152-164">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="75152-165">若要在 [管理員認證] 下執行命令視窗，請按一下 [**開始**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="75152-165">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="75152-166">請記住，這些原則應該針對用戶端電腦進行設定。</span><span class="sxs-lookup"><span data-stu-id="75152-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="75152-167">它們不應該套用到執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="75152-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="75152-168">若要協助確保網路資料包是以適當的 DSCP 值標示，您也應該透過完成下列程式，在每個電腦上建立新的登錄專案：</span><span class="sxs-lookup"><span data-stu-id="75152-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="75152-169">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="75152-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="75152-170">在 [**執行**] 對話方塊中，輸入**regedit** ，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="75152-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="75152-171">在 [登錄編輯程式] 中，展開 [ **HKEY\_本機\_電腦**]，展開 [**系統**]、[ **CurrentControlSet**]、[**服務**]，然後再展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="75152-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="75152-172">以滑鼠右鍵按一下 [ **Tcpip**]，指向 [**新增**]，然後按一下 [**金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="75152-172">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="75152-173">建立新的登錄金鑰之後，請輸入**QoS** ，然後按 enter 來重新命名金鑰。</span><span class="sxs-lookup"><span data-stu-id="75152-173">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="75152-174">以滑鼠右鍵按一下 [ **QoS**]，指向 [**新增**]，然後按一下 [**字串值**]。</span><span class="sxs-lookup"><span data-stu-id="75152-174">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="75152-175">建立新的登錄值之後，請輸入 [**不要使用 NLA** ]，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="75152-175">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="75152-176">按兩下 [**不使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="75152-176">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="75152-177">在 [**編輯字串**] 對話方塊中，于 [**值資料**] 方塊中輸入**1** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="75152-177">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="75152-178">關閉 [登錄編輯程式]，然後重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="75152-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="75152-179">在有多個網路介面卡的電腦上設定品質服務</span><span class="sxs-lookup"><span data-stu-id="75152-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="75152-180">如果您的電腦有多個網路介面卡，您可能偶爾會遇到 DSCP 值顯示為0x00 （而不是設定的值）的問題。</span><span class="sxs-lookup"><span data-stu-id="75152-180">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="75152-181">這通常會發生在電腦上一或多個網路介面卡無法存取您的 Active Directory 網域（例如，如果是針對私人網路使用這些配接器）。</span><span class="sxs-lookup"><span data-stu-id="75152-181">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="75152-182">在這種情況下，會將 DSCP 值標記為可存取網域的配接器，但不會針對無法存取網域的配接器標記。</span><span class="sxs-lookup"><span data-stu-id="75152-182">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="75152-183">如果您想要為電腦中的所有網路介面卡標記 DSCP 值，包括沒有您網域存取權的配接器，則您必須在登錄中新增和設定值。</span><span class="sxs-lookup"><span data-stu-id="75152-183">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="75152-184">完成下列程式，即可完成作業：</span><span class="sxs-lookup"><span data-stu-id="75152-184">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="75152-185">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="75152-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="75152-186">在 [**執行**] 對話方塊中，輸入**regedit** ，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="75152-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="75152-187">在 [登錄編輯程式] 中，展開 [ **HKEY\_本機\_電腦**]，展開 [**系統**]、[ **CurrentControlSet**]、[**服務**]，然後再展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="75152-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="75152-188">如果您沒有看到標示為 [ **QoS** ] 的登錄機碼，請以滑鼠右鍵按一下 [ **Tcpip**]，指向 [**新增**]，然後按一下 [**金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="75152-188">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="75152-189">建立新的金鑰之後，請輸入**QoS** ，然後按 enter 鍵來重新命名該金鑰。</span><span class="sxs-lookup"><span data-stu-id="75152-189">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="75152-190">以滑鼠右鍵按一下 [ **QoS**]，指向 [**新增**]，然後按一下 [**字串值**]。</span><span class="sxs-lookup"><span data-stu-id="75152-190">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="75152-191">建立新的登錄值之後，請輸入 [**不要使用 NLA** ]，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="75152-191">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="75152-192">按兩下 [**不使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="75152-192">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="75152-193">在 [**編輯字串**] 對話方塊中，于 [**值資料**] 方塊中輸入**1** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="75152-193">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="75152-194">建立及設定新的登錄值之後，您需要重新開機電腦，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="75152-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

