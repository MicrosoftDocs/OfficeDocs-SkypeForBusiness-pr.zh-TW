---
title: Lync Server 2013： 在 Windows 7 或 Windows 8 上執行的用戶端設定服務品質原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fdb331a8d0e6a369f67726c755d76ab1d3bec58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="fbe41-102">Lync Server 2013 中設定的服務品質原則，在 Windows 7 或 Windows 8 上執行的用戶端</span><span class="sxs-lookup"><span data-stu-id="fbe41-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbe41-103">_**主題上次修改日期：** 2016年-03-29_</span><span class="sxs-lookup"><span data-stu-id="fbe41-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="fbe41-104">除了指定 Lync 用戶端使用的連接埠範圍，您也必須建立個別的服務品質原則會套用至用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="fbe41-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="fbe41-105">（建立會議、 應用程式及中繼伺服器的服務品質原則應該不會套用至用戶端電腦。）這項資訊只適用於執行 Lync 2013 用戶端，以及 Windows 7 或 Windows 8 的電腦。</span><span class="sxs-lookup"><span data-stu-id="fbe41-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="fbe41-106">下列範例會使用此組連接埠範圍建立音訊與視訊原則：</span><span class="sxs-lookup"><span data-stu-id="fbe41-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbe41-107">用戶端流量類型</span><span class="sxs-lookup"><span data-stu-id="fbe41-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="fbe41-108">連接埠開始</span><span class="sxs-lookup"><span data-stu-id="fbe41-108">Port Start</span></span></th>
<th><span data-ttu-id="fbe41-109">連接埠範圍</span><span class="sxs-lookup"><span data-stu-id="fbe41-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbe41-110">音訊</span><span class="sxs-lookup"><span data-stu-id="fbe41-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="fbe41-111">50020</span><span class="sxs-lookup"><span data-stu-id="fbe41-111">50020</span></span></p></td>
<td><p><span data-ttu-id="fbe41-112">20</span><span class="sxs-lookup"><span data-stu-id="fbe41-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe41-113">影片</span><span class="sxs-lookup"><span data-stu-id="fbe41-113">Video</span></span></p></td>
<td><p><span data-ttu-id="fbe41-114">58000</span><span class="sxs-lookup"><span data-stu-id="fbe41-114">58000</span></span></p></td>
<td><p><span data-ttu-id="fbe41-115">20</span><span class="sxs-lookup"><span data-stu-id="fbe41-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbe41-116">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="fbe41-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="fbe41-117">42000</span><span class="sxs-lookup"><span data-stu-id="fbe41-117">42000</span></span></p></td>
<td><p><span data-ttu-id="fbe41-118">20</span><span class="sxs-lookup"><span data-stu-id="fbe41-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbe41-119">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="fbe41-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="fbe41-120">42020</span><span class="sxs-lookup"><span data-stu-id="fbe41-120">42020</span></span></p></td>
<td><p><span data-ttu-id="fbe41-121">20</span><span class="sxs-lookup"><span data-stu-id="fbe41-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fbe41-122">若要建立的服務品質音訊原則的 Windows 7 或 Windows 8 的電腦，第一次登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="fbe41-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="fbe41-123">開啟群組原則管理] （按一下 [**開始]**、 指向 [**系統管理工具**]，然後按一下 [**群組原則管理**），然後完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="fbe41-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="fbe41-124">在群組原則管理中，找出要用來建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="fbe41-124">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="fbe41-125">例如，如果您所有的用戶端電腦位於名為用戶端 OU 然後新的原則應建立在用戶端的 OU 中。</span><span class="sxs-lookup"><span data-stu-id="fbe41-125">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="fbe41-126">以滑鼠右鍵按一下適當的容器，然後按一下 [在這個網域中建立 GPO 並連結到]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe41-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="fbe41-127">在 [**新增 GPO** ] 對話方塊中，輸入新的群組原則物件的名稱 （例如， **Lync 音訊]**） 中的 [**名稱**] 方塊中，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="fbe41-128">以滑鼠右鍵按一下新建的原則 ，然後按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe41-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="fbe41-129">在群組原則管理編輯器 」 中，展開 [**電腦組態**]、 展開 [**原則**]、 展開 [ **Windows 設定**，以滑鼠右鍵按一下 [**原則式 QoS**]，，然後按一下 [**建立新原則**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="fbe41-130">在 [**原則式 QoS** ] 對話方塊中，在 [開啟] 頁面中，輸入 [**名稱**] 方塊中的新原則 （例如， **Lync 音訊]**） 的名稱。</span><span class="sxs-lookup"><span data-stu-id="fbe41-130">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="fbe41-131">選取 [指定 DSCP 數值]\*\*\*\*，並將該值設為 **46**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-131">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="fbe41-132">將 [指定輸出節流閥速率]\*\*\*\* 保留未選取狀態，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe41-132">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="fbe41-133">在下一個頁面上，選取 [**使用此可執行檔名稱的應用程式**輸入名稱**Lync.exe**，並再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="fbe41-134">此設定會指示來只設定優先順序相符的流量，從 Lync 用戶端原則。</span><span class="sxs-lookup"><span data-stu-id="fbe41-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="fbe41-p106">在第三頁上，確定 [任何來源 IP 位址]\*\*\*\* 及 [任何目的地 IP 位址]\*\*\*\* 都已選取，然後按 [下一步]\*\*\*\*。這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。</span><span class="sxs-lookup"><span data-stu-id="fbe41-p106">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="fbe41-137">在第四頁上，從 [選取此 QoS 原則套用的通訊協定]\*\*\*\* 下拉式清單中選取 [TCP 及 UDP]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe41-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="fbe41-138">（傳輸控制通訊協定） TCP 及 UDP （使用者資料包通訊協定） 是最常使用的 Lync Server 和其用戶端應用程式的兩個網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="fbe41-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="fbe41-139">在**指定的來源連接埠號碼**標題下，選取 [**從這個來源的連接埠或範圍**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-139">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="fbe41-140">在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="fbe41-140">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="fbe41-141">例如，如果您已保留連接埠 50020 透過連接埠 50039 的音訊流量進入使用這種格式的連接埠範圍： **50020:50039**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-141">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="fbe41-142">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe41-142">Click **Finish**.</span></span>

<span data-ttu-id="fbe41-143">當您建立音訊 QoS 原則之後您再應該建立影片的第二個原則。</span><span class="sxs-lookup"><span data-stu-id="fbe41-143">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="fbe41-144">若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：</span><span class="sxs-lookup"><span data-stu-id="fbe41-144">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="fbe41-145">使用不同 （且唯一） 的原則名稱 （例如， **Lync 視訊]**）。</span><span class="sxs-lookup"><span data-stu-id="fbe41-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="fbe41-146">DSCP 值設為**34**而不是 46。</span><span class="sxs-lookup"><span data-stu-id="fbe41-146">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="fbe41-147">（如先前所述，您不需要使用 DSCP 數值 34; 您只是必須指派不同的 DSCP 值所使用的音訊）。</span><span class="sxs-lookup"><span data-stu-id="fbe41-147">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="fbe41-148">為視訊傳輸使用先前設定的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="fbe41-148">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="fbe41-149">例如，如果您已保留連接埠 58000 透過 58019 視訊，然後設定連接埠範圍如下： **58000:58019**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-149">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="fbe41-150">如果您決定建立原則來管理應用程式共用流量請更改以下設定：</span><span class="sxs-lookup"><span data-stu-id="fbe41-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="fbe41-151">使用不同的 (且唯一的) 原則名稱 (例如，**Lync Server Application Sharing**)。</span><span class="sxs-lookup"><span data-stu-id="fbe41-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="fbe41-152">設定的 DSCP 值為**24**而不是 46。</span><span class="sxs-lookup"><span data-stu-id="fbe41-152">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="fbe41-153">（同樣地，此值沒有設為 24; 它只是必須不同於使用的音訊和視訊的 DSCP 值）。</span><span class="sxs-lookup"><span data-stu-id="fbe41-153">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="fbe41-154">為視訊傳輸使用先前設定的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="fbe41-154">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="fbe41-155">例如，如果您已保留連接埠 42000 透過 42019 應用程式共用，然後設定連接埠範圍如下： **42000:42019**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-155">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="fbe41-156">檔案傳輸原則：</span><span class="sxs-lookup"><span data-stu-id="fbe41-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="fbe41-157">使用不同 （且唯一） 的原則名稱 （例如， **Lync 伺服器檔案傳輸**）。</span><span class="sxs-lookup"><span data-stu-id="fbe41-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="fbe41-158">設定的 DSCP 值為**14**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-158">Set the DSCP value to **14**.</span></span> <span data-ttu-id="fbe41-159">（同樣地，此值沒有設為 14; 它只是必須是唯一的 DSCP 程式碼）。</span><span class="sxs-lookup"><span data-stu-id="fbe41-159">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="fbe41-160">應用程式中使用先前設定的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="fbe41-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="fbe41-161">例如，如果您已保留連接埠 42020 透過 42039 應用程式共用，然後設定連接埠範圍如下： **42020:42039**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="fbe41-162">您已建立的新原則不會生效之前已重新整理您的用戶端電腦上的群組原則。</span><span class="sxs-lookup"><span data-stu-id="fbe41-162">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="fbe41-163">雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="fbe41-163">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="fbe41-164">可以從系統管理員認證執行任何命令視窗執行此命令。</span><span class="sxs-lookup"><span data-stu-id="fbe41-164">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="fbe41-165">若要以系統管理員憑證執行命令視窗，請按一下 [開始]\*\*\*\*，以滑鼠右鍵按一下 [命令提示字元]\*\*\*\*，然後按一下 [以系統管理員身分執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe41-165">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="fbe41-166">請記住，這些原則應已設定目標向用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="fbe41-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="fbe41-167">它們不應該套用到執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="fbe41-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="fbe41-168">為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="fbe41-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="fbe41-169">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe41-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="fbe41-170">在 [執行]\*\*\*\* 對話方塊中，輸入 **regedit**，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="fbe41-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="fbe41-171">在登錄編輯程式中，依序展開 [ **HKEY\_本機\_機器**、 展開 [**系統**、 [ **CurrentControlSet**、 展開 [**服務**] 及 [ **tcpip]**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="fbe41-p119">以滑鼠右鍵按一下 [Tcpip]\*\*\*\*，指向 [新增]\*\*\*\*，然後按一下 [索引鍵]\*\*\*\*。建立新的登錄機碼之後，輸入 **QoS**，然後按 ENTER 鍵，以將索引鍵重新命名。</span><span class="sxs-lookup"><span data-stu-id="fbe41-p119">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="fbe41-p120">以滑鼠右鍵按一下 [QoS]\*\*\*\*，指向 [新增]\*\*\*\*，然後按一下 [字串值]\*\*\*\*。建立新的登錄值之後，輸入 **Do not use NLA**，然後按 ENTER 鍵，以將該值重新命名。</span><span class="sxs-lookup"><span data-stu-id="fbe41-p120">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="fbe41-176">連按兩下 [**不使用 NLA**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-176">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="fbe41-177">在 [編輯字串]\*\*\*\* 對話方塊的 [數值資料]\*\*\*\* 方塊中輸入 **1**，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe41-177">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="fbe41-178">關閉登錄編輯程式，然後重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="fbe41-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="fbe41-179">在具有多個網路介面卡的電腦上設定服務品質</span><span class="sxs-lookup"><span data-stu-id="fbe41-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="fbe41-180">如果您有多個網路介面卡的電腦可能會偶爾會遇到其中 DSCP 值顯示為 0x00 的問題，而不是設定的值。</span><span class="sxs-lookup"><span data-stu-id="fbe41-180">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="fbe41-181">這通常會發生在一或多個網路介面卡不能夠存取您的 Active Directory 網域 （例如，如果這些介面卡用於私人網路） 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="fbe41-181">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="fbe41-182">在這類的情況下，DSCP 值將會標記為可以存取該網域，但不會標記為無法存取之網域的介面卡的介面卡。</span><span class="sxs-lookup"><span data-stu-id="fbe41-182">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="fbe41-183">如果您想要在電腦上，包括您的網域，不需要存取的介面卡的所有網路介面卡的標記 DSCP 值，將需要新增及設定的登錄值。</span><span class="sxs-lookup"><span data-stu-id="fbe41-183">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="fbe41-184">可以藉由完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="fbe41-184">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="fbe41-185">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe41-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="fbe41-186">在 [執行]\*\*\*\* 對話方塊中，輸入 **regedit**，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="fbe41-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="fbe41-187">在登錄編輯程式中，依序展開 [ **HKEY\_本機\_機器**、 展開 [**系統**、 [ **CurrentControlSet**、 展開 [**服務**] 及 [ **tcpip]**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="fbe41-188">如果看不到登錄機碼，然後標示**QoS** **Tcpip**上按一下滑鼠右鍵，指向 [**新增**]，然後按一下 [**機碼**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-188">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="fbe41-189">建立新的金鑰之後，輸入**QoS** ，然後按 ENTER，以重新命名機碼。</span><span class="sxs-lookup"><span data-stu-id="fbe41-189">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="fbe41-p125">以滑鼠右鍵按一下 [QoS]\*\*\*\*，指向 [新增]\*\*\*\*，然後按一下 [字串值]\*\*\*\*。建立新的登錄值之後，輸入 **Do not use NLA**，然後按 ENTER 鍵，以將該值重新命名。</span><span class="sxs-lookup"><span data-stu-id="fbe41-p125">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="fbe41-192">連按兩下 [**不使用 NLA**。</span><span class="sxs-lookup"><span data-stu-id="fbe41-192">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="fbe41-193">在 [編輯字串]\*\*\*\* 對話方塊的 [數值資料]\*\*\*\* 方塊中輸入 **1**，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe41-193">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="fbe41-194">建立及設定新的登錄值之後，您必須重新啟動電腦，為了讓變更生效。</span><span class="sxs-lookup"><span data-stu-id="fbe41-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

