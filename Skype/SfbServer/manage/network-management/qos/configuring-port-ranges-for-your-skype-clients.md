---
title: 為用戶端設定埠範圍和服務品質原則
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文說明如何為您的用戶端設定埠範圍, 以及如何在執行 Windows 10 之用戶端的商務用 Skype Server 中設定品質原則。
ms.openlocfilehash: 4d7999634864e222dd627ea3b46a3a3da5c67fe5
ms.sourcegitcommit: 67282b5f2f1aac3e675c4a485f4846deba15deb4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/24/2019
ms.locfileid: "36194120"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="bd45b-103">在商務用 Skype Server 中針對用戶端設定埠範圍和服務品質原則</span><span class="sxs-lookup"><span data-stu-id="bd45b-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="bd45b-104">本文說明如何為您的用戶端設定埠範圍, 以及如何在執行 Windows 10 之用戶端的商務用 Skype Server 中設定品質原則。</span><span class="sxs-lookup"><span data-stu-id="bd45b-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="bd45b-105">設定埠範圍</span><span class="sxs-lookup"><span data-stu-id="bd45b-105">Configure port ranges</span></span>

<span data-ttu-id="bd45b-106">根據預設, 商務用 Skype 用戶端應用程式在通訊會話中參與時, 可以使用埠1024和65535之間的任何埠;這是因為不會針對用戶端自動啟用特定的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="bd45b-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="bd45b-107">不過, 若要使用服務品質, 您需要將各種類型的流量 (音訊、影片、媒體、應用程式共用及檔案傳輸) 重新指派到一系列的唯一端口範圍。</span><span class="sxs-lookup"><span data-stu-id="bd45b-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="bd45b-108">您可以使用 CsConferencingConfiguration Cmdlet 來完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="bd45b-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="bd45b-109">最終使用者無法自行進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="bd45b-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="bd45b-110">只有系統管理員才能使用 CsConferencingConfiguration Cmdlet 進行埠變更。</span><span class="sxs-lookup"><span data-stu-id="bd45b-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="bd45b-111">您可以從商務用 Skype Server Management 命令介面中執行下列命令, 以判斷通訊會話目前使用的是哪個埠範圍:</span><span class="sxs-lookup"><span data-stu-id="bd45b-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="bd45b-112">假設您在安裝商務用 Skype Server 之後, 您還沒有對會議設定進行任何變更, 您應該會返回包含這些屬性值的資訊:</span><span class="sxs-lookup"><span data-stu-id="bd45b-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="bd45b-113">如果您仔細查看上述輸出, 您會看到兩個重要事項。</span><span class="sxs-lookup"><span data-stu-id="bd45b-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="bd45b-114">首先, ClientMediaPortRangeEnabled 屬性會設定為 False:</span><span class="sxs-lookup"><span data-stu-id="bd45b-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="bd45b-115">這很重要, 因為當這個屬性設定為 False 時, 商務用 Skype 用戶端會在通訊會話中涉及埠1024和65535之間的任何可用埠;無論任何其他的埠設定 (例如, ClientMediaPort 或 ClientVideoPort), 都是如此。</span><span class="sxs-lookup"><span data-stu-id="bd45b-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="bd45b-116">如果您想要將使用量限制在指定的一組埠 (如果您打算執行服務品質, 這是您想要執行的動作), 則必須先啟用用戶端媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="bd45b-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="bd45b-117">可以使用下列 Windows PowerShell 命令完成:</span><span class="sxs-lookup"><span data-stu-id="bd45b-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="bd45b-118">上述命令可讓用戶端媒體埠範圍用於全域集合會議設定。不過, 這些設定也可以套用至網站範圍和/或服務範圍 (僅適用于會議服務器服務)。</span><span class="sxs-lookup"><span data-stu-id="bd45b-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="bd45b-119">若要啟用特定網站或伺服器的用戶端媒體埠範圍, 請在呼叫 Set-CsConferencingConfiguration 時指定該網站或伺服器的身分識別:</span><span class="sxs-lookup"><span data-stu-id="bd45b-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="bd45b-120">或者, 您也可以使用此命令同時啟用所有會議設定的埠範圍:</span><span class="sxs-lookup"><span data-stu-id="bd45b-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="bd45b-121">您會注意到的第二個重要事項是, 樣本輸出顯示針對每種類型的網路流量所設定的媒體埠範圍是完全相同的:</span><span class="sxs-lookup"><span data-stu-id="bd45b-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="bd45b-122">為了實現 QoS, 這些埠範圍中的每一個都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bd45b-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="bd45b-123">例如, 您可以設定埠範圍, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="bd45b-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd45b-124">用戶端流量類型</span><span class="sxs-lookup"><span data-stu-id="bd45b-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="bd45b-125">埠開始</span><span class="sxs-lookup"><span data-stu-id="bd45b-125">Port Start</span></span></th>
<th><span data-ttu-id="bd45b-126">埠範圍</span><span class="sxs-lookup"><span data-stu-id="bd45b-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd45b-127">音訊</span><span class="sxs-lookup"><span data-stu-id="bd45b-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="bd45b-128">50020</span><span class="sxs-lookup"><span data-stu-id="bd45b-128">50020</span></span></p></td>
<td><p><span data-ttu-id="bd45b-129">20</span><span class="sxs-lookup"><span data-stu-id="bd45b-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd45b-130">顯示器</span><span class="sxs-lookup"><span data-stu-id="bd45b-130">Video</span></span></p></td>
<td><p><span data-ttu-id="bd45b-131">58000</span><span class="sxs-lookup"><span data-stu-id="bd45b-131">58000</span></span></p></td>
<td><p><span data-ttu-id="bd45b-132">20</span><span class="sxs-lookup"><span data-stu-id="bd45b-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd45b-133">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="bd45b-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="bd45b-134">42000</span><span class="sxs-lookup"><span data-stu-id="bd45b-134">42000</span></span></p></td>
<td><p><span data-ttu-id="bd45b-135">20</span><span class="sxs-lookup"><span data-stu-id="bd45b-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd45b-136">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="bd45b-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="bd45b-137">42020</span><span class="sxs-lookup"><span data-stu-id="bd45b-137">42020</span></span></p></td>
<td><p><span data-ttu-id="bd45b-138">20</span><span class="sxs-lookup"><span data-stu-id="bd45b-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bd45b-139">在前一個表格中, 用戶端埠範圍代表伺服器設定的埠範圍的子集。</span><span class="sxs-lookup"><span data-stu-id="bd45b-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="bd45b-140">例如, 在伺服器上, 應用程式共用已設定為使用埠40803到 49151;在用戶端電腦上, 應用程式共用設定為使用埠42000到42019。</span><span class="sxs-lookup"><span data-stu-id="bd45b-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="bd45b-141">如此一來, 主要是為了更輕鬆地管理 QoS: 用戶端埠不需要代表在伺服器上使用的埠子集。</span><span class="sxs-lookup"><span data-stu-id="bd45b-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="bd45b-142">(例如, 您可以在用戶端電腦上設定要使用的應用程式共用, 比如說埠10000到10019。)不過, 建議您將用戶端埠範圍設為伺服器埠範圍的子集。</span><span class="sxs-lookup"><span data-stu-id="bd45b-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="bd45b-143">此外, 您可能已經注意到8348埠已針對伺服器上的應用程式共用而設定, 但用戶端上的應用程式共用只留有20個埠。</span><span class="sxs-lookup"><span data-stu-id="bd45b-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="bd45b-144">我們也建議您這麼做, 但不是很難且快速的規則。</span><span class="sxs-lookup"><span data-stu-id="bd45b-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="bd45b-145">一般來說, 您可以考慮每個可用的埠代表單一通訊會話: 如果您的埠範圍中有100埠, 這表示有問題的電腦在任何特定時間都可以參與到100通訊會話。</span><span class="sxs-lookup"><span data-stu-id="bd45b-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="bd45b-146">因為伺服器可能會參與許多用戶端的交談, 所以在伺服器上開啟的埠數會比用戶端多。</span><span class="sxs-lookup"><span data-stu-id="bd45b-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="bd45b-147">為用戶端上的應用程式共用設定20個埠, 意味著使用者可以同時在指定的裝置上參與20個應用程式共用會話。</span><span class="sxs-lookup"><span data-stu-id="bd45b-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="bd45b-148">這對於絕大多數使用者而言, 都應該有足夠的證明。</span><span class="sxs-lookup"><span data-stu-id="bd45b-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="bd45b-149">若要將先前的埠範圍指派給您的全域會議設定設定, 您可以使用下列商務用 Skype Server Management Shell 命令:</span><span class="sxs-lookup"><span data-stu-id="bd45b-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="bd45b-150">或者, 您可以使用這個命令, 為所有的會議設定指派相同的埠範圍:</span><span class="sxs-lookup"><span data-stu-id="bd45b-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="bd45b-151">個別使用者必須從商務用 Skype 登出, 然後重新登入, 這些變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="bd45b-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="bd45b-152">您也可以使用單一命令來啟用用戶端媒體埠範圍, 然後指派這些埠範圍。</span><span class="sxs-lookup"><span data-stu-id="bd45b-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="bd45b-153">例如：</span><span class="sxs-lookup"><span data-stu-id="bd45b-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="bd45b-154">設定在 Windows 10 上執行之用戶端的服務品質原則</span><span class="sxs-lookup"><span data-stu-id="bd45b-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="bd45b-155">除了指定要供商務用 Skype 用戶端使用的埠範圍之外, 您還必須建立會套用至用戶端電腦的個別服務品質。</span><span class="sxs-lookup"><span data-stu-id="bd45b-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="bd45b-156">(針對會議、應用程式和中繼伺服器所建立的服務品質原則, 不應該套用到用戶端電腦。)此資訊僅適用于執行商務用 Skype 用戶端和 Windows 10 的電腦。</span><span class="sxs-lookup"><span data-stu-id="bd45b-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="bd45b-157">下列範例使用這組埠範圍來建立音訊原則和影片原則:</span><span class="sxs-lookup"><span data-stu-id="bd45b-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd45b-158">用戶端流量類型</span><span class="sxs-lookup"><span data-stu-id="bd45b-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="bd45b-159">埠開始</span><span class="sxs-lookup"><span data-stu-id="bd45b-159">Port Start</span></span></th>
<th><span data-ttu-id="bd45b-160">埠範圍</span><span class="sxs-lookup"><span data-stu-id="bd45b-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd45b-161">音訊</span><span class="sxs-lookup"><span data-stu-id="bd45b-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="bd45b-162">50020</span><span class="sxs-lookup"><span data-stu-id="bd45b-162">50020</span></span></p></td>
<td><p><span data-ttu-id="bd45b-163">20</span><span class="sxs-lookup"><span data-stu-id="bd45b-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd45b-164">顯示器</span><span class="sxs-lookup"><span data-stu-id="bd45b-164">Video</span></span></p></td>
<td><p><span data-ttu-id="bd45b-165">58000</span><span class="sxs-lookup"><span data-stu-id="bd45b-165">58000</span></span></p></td>
<td><p><span data-ttu-id="bd45b-166">20</span><span class="sxs-lookup"><span data-stu-id="bd45b-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd45b-167">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="bd45b-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="bd45b-168">42000</span><span class="sxs-lookup"><span data-stu-id="bd45b-168">42000</span></span></p></td>
<td><p><span data-ttu-id="bd45b-169">20</span><span class="sxs-lookup"><span data-stu-id="bd45b-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd45b-170">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="bd45b-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="bd45b-171">42020</span><span class="sxs-lookup"><span data-stu-id="bd45b-171">42020</span></span></p></td>
<td><p><span data-ttu-id="bd45b-172">20</span><span class="sxs-lookup"><span data-stu-id="bd45b-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd45b-173">若要建立適用于 Windows 10 電腦的服務品質音訊原則, 請先登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="bd45b-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="bd45b-174">開啟 [群組原則管理] (按一下 [**開始**], 指向 [系統**管理工具**], 然後按一下 [**群組原則管理**]), 然後完成下列程式:</span><span class="sxs-lookup"><span data-stu-id="bd45b-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="bd45b-175">在 [群組原則管理] 中, 找出要建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="bd45b-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="bd45b-176">例如, 如果所有用戶端電腦都位於一個名為「用戶端」的 OU 中, 則應該在用戶端 OU 中建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="bd45b-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="bd45b-177">以滑鼠右鍵按一下適當的容器, 然後按一下 [**在這個網域建立 GPO], 然後在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="bd45b-178">在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中, 輸入新群組原則物件的名稱, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="bd45b-179">以滑鼠右鍵按一下新建立的原則, 然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="bd45b-180">在 [群組原則管理編輯器] 中, 展開 [**電腦**設定], 展開 [ **Windows 設定**], 以滑鼠右鍵按一下 [**原則式 QoS**], 然後按一下 [**建立新策略**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="bd45b-181">在 [**原則式 QoS** ] 對話方塊的 [開始] 頁面上, 于 [**名稱**] 方塊中輸入新原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="bd45b-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="bd45b-182">選取 [**指定 DSCP 值**], 然後將值設定為**46**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="bd45b-183">[離開]**指定輸出限制率**未選取, 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="bd45b-184">在下一頁上, 選取 [**僅限具有此可執行檔名稱的應用程式**], 輸入**Lync**作為名稱, 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="bd45b-185">這個設定會指示原則只會將商務用 Skype 用戶端的通訊順序設成優先順序。</span><span class="sxs-lookup"><span data-stu-id="bd45b-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="bd45b-186">在第三個頁面上, 確認已選取 [**所有來源 ip 位址**] 和 [**任何目的地 ip 位址**], 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="bd45b-187">這兩項設定可確保無論哪些電腦 (IP 位址) 傳送這些資料包, 以及哪些電腦 (IP 位址) 會接收那些資料包, 都會管理資料包。</span><span class="sxs-lookup"><span data-stu-id="bd45b-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="bd45b-188">在第4頁, 從 [**選取此 QoS 原則適用**于] 下拉式清單中選取 [ **TCP 和 UDP** ]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="bd45b-189">TCP (傳輸控制通訊協定) 和 UDP (使用者資料包通訊協定) 是商務用 Skype Server 及其用戶端應用程式最常用的兩種網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="bd45b-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="bd45b-190">在 [標題] 底下,**指定來源埠號**, 選取 [**從此來源埠或範圍**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="bd45b-191">在隨附的文字方塊中, 輸入為音訊廣播保留的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="bd45b-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="bd45b-192">例如, 如果您是透過埠50039將埠50020預留給音訊流量, 請輸入使用此格式的埠範圍: **50020:50039**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="bd45b-193">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-193">Click **Finish**.</span></span>

<span data-ttu-id="bd45b-194">在您建立音訊的 QoS 原則之後, 您應該先建立影片的第二個原則。</span><span class="sxs-lookup"><span data-stu-id="bd45b-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="bd45b-195">若要建立影片的原則, 請遵循您在建立音訊原則時所遵循的基本程式, 進行這些替換:</span><span class="sxs-lookup"><span data-stu-id="bd45b-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="bd45b-196">使用不同 (且唯一的) 原則名稱。</span><span class="sxs-lookup"><span data-stu-id="bd45b-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="bd45b-197">將 DSCP 值設為**34** , 而不是46。</span><span class="sxs-lookup"><span data-stu-id="bd45b-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="bd45b-198">(如前所述, 您不需要使用 DSCP 值 34; 您只需指派不同于音訊所用的 DSCP 值即可)。</span><span class="sxs-lookup"><span data-stu-id="bd45b-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="bd45b-199">使用先前設定的影片流量埠範圍。</span><span class="sxs-lookup"><span data-stu-id="bd45b-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="bd45b-200">例如, 如果您已將埠58000到58019的備用, 請將埠範圍設定為: **58000:58019**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="bd45b-201">如果您決定建立用來管理應用程式共用流量的原則, 請進行下列替換:</span><span class="sxs-lookup"><span data-stu-id="bd45b-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="bd45b-202">使用不同 (且唯一的) 原則名稱 (例如,**商務用 Skype Server 應用程式共用**)。</span><span class="sxs-lookup"><span data-stu-id="bd45b-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="bd45b-203">將 DSCP 值設為**24** , 而不是46。</span><span class="sxs-lookup"><span data-stu-id="bd45b-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="bd45b-204">(同樣地, 此值不一定必須是 24; 它必須與用於音訊和影片的 DSCP 值不同)。</span><span class="sxs-lookup"><span data-stu-id="bd45b-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="bd45b-205">使用先前設定的影片流量埠範圍。</span><span class="sxs-lookup"><span data-stu-id="bd45b-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="bd45b-206">例如, 如果您已在應用程式共用中保留埠42000到 42019, 請將埠範圍設定為: **42000:42019**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="bd45b-207">針對檔案傳輸原則:</span><span class="sxs-lookup"><span data-stu-id="bd45b-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="bd45b-208">使用不同 (且唯一的) 原則名稱 (例如,**商務用 Skype Server 檔案傳輸**)。</span><span class="sxs-lookup"><span data-stu-id="bd45b-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="bd45b-209">將 DSCP 值設為**14**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="bd45b-210">(同樣地, 這個值不一定是 14; 它必須是唯一的 DSCP 代碼。)</span><span class="sxs-lookup"><span data-stu-id="bd45b-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="bd45b-211">使用先前設定的應用程式埠範圍。</span><span class="sxs-lookup"><span data-stu-id="bd45b-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="bd45b-212">例如, 如果您已在應用程式共用中保留埠42020到 42039, 請將埠範圍設定為: **42020:42039**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="bd45b-213">您所建立的新原則必須在用戶端電腦上重新整理群組原則後才會生效。</span><span class="sxs-lookup"><span data-stu-id="bd45b-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="bd45b-214">雖然群組原則會定期自行進行重新整理, 但是您可以在需要重新整理群組原則的每一台電腦上執行下列命令, 以強制立即重新整理:</span><span class="sxs-lookup"><span data-stu-id="bd45b-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="bd45b-215">這個命令可以從任何執行在「管理員認證」的命令視窗中執行。</span><span class="sxs-lookup"><span data-stu-id="bd45b-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="bd45b-216">若要在 [管理員認證] 下執行命令視窗, 請按一下 [**開始**], 以滑鼠右鍵按一下**命令提示**字元, 然後按一下 [**以系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="bd45b-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="bd45b-217">請記住, 這些原則應該針對用戶端電腦進行設定。</span><span class="sxs-lookup"><span data-stu-id="bd45b-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="bd45b-218">它們不應該套用到執行商務用 Skype Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="bd45b-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="bd45b-219">若要協助確保網路資料包是以適當的 DSCP 值標示, 您也應該透過完成下列程式, 在每個電腦上建立新的登錄專案:</span><span class="sxs-lookup"><span data-stu-id="bd45b-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="bd45b-220">按一下 [**開始**], 然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="bd45b-221">在 [**執行**] 對話方塊中, 輸入**regedit**, 然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="bd45b-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="bd45b-222">在 [登錄編輯程式] 中, 展開 [ **HKEY\_本機\_電腦**], 展開 [**系統**]、[ **CurrentControlSet**]、[**服務**], 然後再展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="bd45b-223">以滑鼠右鍵按一下 [ **Tcpip**], 指向 [**新增**], 然後按一下 [**金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="bd45b-224">建立新的登錄金鑰之後, 請輸入**QoS**, 然後按 enter 來重新命名金鑰。</span><span class="sxs-lookup"><span data-stu-id="bd45b-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="bd45b-225">以滑鼠右鍵按一下 [ **QoS**], 指向 [**新增**], 然後按一下 [**字串值**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="bd45b-226">建立新的登錄值之後, 請輸入 [**不使用 NLA**], 然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="bd45b-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="bd45b-227">按兩下 [**不使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="bd45b-228">在 [**編輯字串**] 對話方塊中, 于 [**值資料**] 方塊中輸入**1** , 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="bd45b-229">關閉 [登錄編輯程式], 然後 eboot 您的電腦。</span><span class="sxs-lookup"><span data-stu-id="bd45b-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="bd45b-230">在有多個網路介面卡的電腦上設定服務品質</span><span class="sxs-lookup"><span data-stu-id="bd45b-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="bd45b-231">如果您的電腦有多個網路介面卡, 您可能偶爾會遇到 DSCP 值顯示為 0x00 (而不是設定的值) 的問題。</span><span class="sxs-lookup"><span data-stu-id="bd45b-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="bd45b-232">這通常會發生在電腦上一或多個網路介面卡無法存取您的 Active Directory 網域 (例如, 如果是針對私人網路使用這些配接器)。</span><span class="sxs-lookup"><span data-stu-id="bd45b-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="bd45b-233">在這種情況下, 會將 DSCP 值標記為可存取網域的配接器, 但不會針對無法存取網域的配接器標記。</span><span class="sxs-lookup"><span data-stu-id="bd45b-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="bd45b-234">如果您想要為電腦中的所有網路介面卡標示 DSCP 值, 包括沒有您網域存取權的配接器, 您必須在註冊表中新增並設定值。</span><span class="sxs-lookup"><span data-stu-id="bd45b-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="bd45b-235">完成下列程式, 即可完成作業:</span><span class="sxs-lookup"><span data-stu-id="bd45b-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="bd45b-236">按一下 [**開始**], 然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="bd45b-237">在 [**執行**] 對話方塊中, 輸入**regedit**, 然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="bd45b-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="bd45b-238">在 [登錄編輯程式] 中, 展開 [ **HKEY\_本機\_電腦**], 展開 [**系統**]、[ **CurrentControlSet**]、[**服務**], 然後再展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="bd45b-239">如果您沒有看到標示為 [ **QoS** ] 的登錄機碼, 請以滑鼠右鍵按一下 [ **Tcpip**], 指向 [**新增**], 然後按一下 [**金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="bd45b-240">建立新的金鑰之後, 請輸入**QoS**, 然後按 enter 來重新命名金鑰。</span><span class="sxs-lookup"><span data-stu-id="bd45b-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="bd45b-241">以滑鼠右鍵按一下 [ **QoS**], 指向 [**新增**], 然後按一下 [**字串值**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="bd45b-242">建立新的登錄值之後, 請輸入 [**不使用 NLA**], 然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="bd45b-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="bd45b-243">按兩下 [**不使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="bd45b-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="bd45b-244">在 [**編輯字串**] 對話方塊中, 于 [**值資料**] 方塊中輸入**1** , 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bd45b-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="bd45b-245">建立並設定新的登錄值之後, 您必須重新開機電腦, 變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="bd45b-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd45b-246">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bd45b-246">See also</span></span>

[<span data-ttu-id="bd45b-247">在 Windows 10 中建立群組原則物件</span><span class="sxs-lookup"><span data-stu-id="bd45b-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
