---
title: 針對立即訊息（IM）設定檔案傳輸與 URL 篩選
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="a0190-102">在 Lync Server 2013 中設定立即訊息（IM）的檔案傳輸與 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="a0190-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0190-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a0190-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a0190-104">智慧 IM 篩選工具可協助保護您的 Lync Server 2013 部署，避免受到最常見的病毒傳播，以及最小限度地降低使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="a0190-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="a0190-105">使用智慧 IM 篩選來設定篩選器，以封鎖來自公司防火牆以外的來自未知端點的未經請求或可能有害的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="a0190-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="a0190-106">您可以透過指定準則來決定要封鎖哪些專案（例如包含特定首碼的超連結，以及具有特定副檔名的檔案），來設定篩選。</span><span class="sxs-lookup"><span data-stu-id="a0190-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="a0190-107">智慧 IM 篩選提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="a0190-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="a0190-108">增強的 URL 篩選。</span><span class="sxs-lookup"><span data-stu-id="a0190-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="a0190-109">增強的檔案傳輸篩選。</span><span class="sxs-lookup"><span data-stu-id="a0190-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="a0190-110">設定智慧 IM 篩選包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="a0190-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="a0190-111">設定 URL 篩選。</span><span class="sxs-lookup"><span data-stu-id="a0190-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="a0190-112">配置檔案傳輸篩選。</span><span class="sxs-lookup"><span data-stu-id="a0190-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="a0190-113">如何將篩選選項套用至立即訊息</span><span class="sxs-lookup"><span data-stu-id="a0190-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="a0190-114">在您部署智慧 IM 訊息篩選工具之前，您必須瞭解如何套用篩選選項，因為郵件是從一個 Lync Server 2013 伺服器路由到另一個。</span><span class="sxs-lookup"><span data-stu-id="a0190-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="a0190-115">套用這些篩選選項的方式是一致的，不論伺服器是位於單一組織中，還是跨組織界限。</span><span class="sxs-lookup"><span data-stu-id="a0190-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="a0190-116">此一致性會套用至將自訂通知與警告文字插入郵件中並在伺服器之間傳送的方式。</span><span class="sxs-lookup"><span data-stu-id="a0190-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a0190-117">[立即訊息] 篩選會增加處理郵件中的 Url 所需的 CPU 資源量。</span><span class="sxs-lookup"><span data-stu-id="a0190-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="a0190-118">這種 CPU 需求增加也會影響 Lync Server 的效能。</span><span class="sxs-lookup"><span data-stu-id="a0190-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="a0190-119">透過使用 [Lync Server 控制台] 中的 [ **IM 和目前狀態**] 群組中的 [ **URL 篩選**] 頁面，您可以封鎖部分或所有的超連結，或設定警告。</span><span class="sxs-lookup"><span data-stu-id="a0190-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="a0190-120">當您選擇 [**超連結首碼**] 選項 [**傳送警告訊息**] 時，會在包含超連結的立即訊息開頭插入警告。</span><span class="sxs-lookup"><span data-stu-id="a0190-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="a0190-121">當立即訊息從一個伺服器傳送到另一個伺服器時，請遵循下列一般指導方針：</span><span class="sxs-lookup"><span data-stu-id="a0190-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="a0190-122">如果伺服器封鎖立即訊息（因為您在 [ **URL 篩選**] 頁面上選取了 [**以檔案副檔名封鎖 url** ] 核取方塊，或是因為您選擇的是 [**超連結首碼**] 選項**區塊超連結**），則會傳回錯誤訊息給用戶端。</span><span class="sxs-lookup"><span data-stu-id="a0190-122">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client.</span></span> <span data-ttu-id="a0190-123">後續伺服器不會收到這則立即訊息。</span><span class="sxs-lookup"><span data-stu-id="a0190-123">Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="a0190-124">如果伺服器（Server1）在包含作用中超連結的立即訊息中新增警告，則在立即訊息中出現的後續伺服器（Server2）會根據此使用中的超連結，繼續進行其他動作並封鎖[立即訊息] 或 [新增警告]。</span><span class="sxs-lookup"><span data-stu-id="a0190-124">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning.</span></span> <span data-ttu-id="a0190-125">如果 Server2 只設定為針對此 URL 新增警告，則會移除 Server1 所新增的舊版警告，並將在 Server2 上設定的警告新增至立即訊息的開頭。</span><span class="sxs-lookup"><span data-stu-id="a0190-125">If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a0190-126">如果您在混合式環境中執行 Lync Server 2013，則使用 [即時通訊伺服器 2005] 與 SP1 是使用智慧 IM 篩選應用程式所需的最低版本。</span><span class="sxs-lookup"><span data-stu-id="a0190-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="a0190-127">即時通訊伺服器2005不支援智慧 IM 篩選器（沒有 SP1）。</span><span class="sxs-lookup"><span data-stu-id="a0190-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="a0190-128">URL 篩選</span><span class="sxs-lookup"><span data-stu-id="a0190-128">URL Filtering</span></span>

<span data-ttu-id="a0190-129">Url 會根據其超連結首碼篩選。</span><span class="sxs-lookup"><span data-stu-id="a0190-129">URLs are filtered according to their hyperlink prefix.</span></span> <span data-ttu-id="a0190-130">下列範例是有效的首碼：</span><span class="sxs-lookup"><span data-stu-id="a0190-130">The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="a0190-131">www\*。</span><span class="sxs-lookup"><span data-stu-id="a0190-131">www\*.</span></span>

  - <span data-ttu-id="a0190-132">ftp.</span><span class="sxs-lookup"><span data-stu-id="a0190-132">ftp.</span></span>

  - <span data-ttu-id="a0190-133">HTTP</span><span class="sxs-lookup"><span data-stu-id="a0190-133">http:</span></span>

<span data-ttu-id="a0190-134">如果您沒有設定立即訊息篩選來執行任何 URL 篩選，立即訊息中包含的所有 Url 都會透過伺服器進行未修改的傳送。</span><span class="sxs-lookup"><span data-stu-id="a0190-134">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server.</span></span> <span data-ttu-id="a0190-135">如果您設定立即訊息篩選來執行 URL 篩選，立即訊息中的 Url 會根據您在 [**編輯 URL 篩選**] 或 [**新增 url 篩選**] 對話方塊中選取的選項進行篩選。</span><span class="sxs-lookup"><span data-stu-id="a0190-135">If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="a0190-136">**啟用 url 篩選**   ：此選項可為全域部署或您選取的網站啟用 URL 篩選。</span><span class="sxs-lookup"><span data-stu-id="a0190-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="a0190-137">**使用副檔名**   來封鎖 url：立即訊息篩選會封鎖任何作用中的內部網路 intranet 或網際網路 URL，其中包含的副檔名會列在 [編輯檔案**篩選器**] 對話方塊中的 [檔案**類型延伸**] 底下。</span><span class="sxs-lookup"><span data-stu-id="a0190-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="a0190-138">當 URL 被封鎖時，寄件者會顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a0190-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="a0190-139">選取此選項時，此選項優先于**將 [檔案類型延伸**] 下所定義之任何副檔名的所有其他篩選選項。</span><span class="sxs-lookup"><span data-stu-id="a0190-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="a0190-140">檔案延伸的篩選只能是標準的檔案名。</span><span class="sxs-lookup"><span data-stu-id="a0190-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="a0190-141">篩選可能無法搭配內嵌在其他名稱中的副檔名。</span><span class="sxs-lookup"><span data-stu-id="a0190-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="a0190-142">若要設定在立即訊息交談中處理超連結的方式，請在 [**超連結前置**詞] 下，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="a0190-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="a0190-143">**請勿**   在郵件中篩選 url 會透過伺服器傳送。</span><span class="sxs-lookup"><span data-stu-id="a0190-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="a0190-144">當您選擇此選項時，會出現 [**允許] 消息**框。</span><span class="sxs-lookup"><span data-stu-id="a0190-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="a0190-145">在 [**允許訊息**] 方塊中，指定您要在包含超連結的每一條立即訊息開頭插入的通知。</span><span class="sxs-lookup"><span data-stu-id="a0190-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="a0190-146">此通知可包含的字元不超過65535個。</span><span class="sxs-lookup"><span data-stu-id="a0190-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="a0190-147">**[封鎖超連結**   ]：由 Lync Server 封鎖包含活動超連結的立即訊息，且寄件者會顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a0190-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="a0190-148">**傳送警告訊息**   Lync Server 允許立即訊息中的活動超連結，但包含警告。</span><span class="sxs-lookup"><span data-stu-id="a0190-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="a0190-149">當您選擇此選項時，會出現**警告訊息**。</span><span class="sxs-lookup"><span data-stu-id="a0190-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="a0190-150">在 [**警告訊息**] 方塊中，您必須輸入您想要在包含有效超連結的立即訊息中包含的警告。</span><span class="sxs-lookup"><span data-stu-id="a0190-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="a0190-151">例如，此警告可能會顯示按一下未知連結的潛在危險，或者可能會參照貴組織的相關原則與需求。</span><span class="sxs-lookup"><span data-stu-id="a0190-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="a0190-152">警告不能超過65535個字元。</span><span class="sxs-lookup"><span data-stu-id="a0190-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="a0190-153">如果您選取 [**封鎖超連結**] 或 [**傳送警告訊息**]，就可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="a0190-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="a0190-154">**排除本機內部網路超連結**   [立即訊息篩選] 只會封鎖網際網路 url。</span><span class="sxs-lookup"><span data-stu-id="a0190-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="a0190-155">內部網路中的位置 Url 會透過伺服器進行未修改的傳送。</span><span class="sxs-lookup"><span data-stu-id="a0190-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="a0190-156">不過，個別伺服器執行 Lync Server 所需的 intranet Url，取決於哪些類型的本機網站被視為其內部網路區域的一部分。</span><span class="sxs-lookup"><span data-stu-id="a0190-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="a0190-157">若要檢查伺服器的 intranet 區域設定，請參閱在[Lync server 2013 中修改預設 URL 篩選器](lync-server-2013-modify-the-default-url-filter.md)中的「在 Internet Explorer 中設定 intranet 設定」程式。</span><span class="sxs-lookup"><span data-stu-id="a0190-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="a0190-158">**篩選這些超連結首碼**   若要選擇要封鎖的首碼，請按一下 [**選取**]，然後在 [**選取超連結首碼**] 中，將 [首碼] 新增到 [**超連結首碼**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="a0190-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="a0190-159">**Href**以外的所有首碼，都必須以句號或冒號結尾，或是星號接著是句號。</span><span class="sxs-lookup"><span data-stu-id="a0190-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="a0190-160">有效的首碼可以包含一組有效 URL 字元（星號（\*）除外）中的任何字元。</span><span class="sxs-lookup"><span data-stu-id="a0190-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="a0190-161">有效的 URL 字元集合\# \*為： +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^\_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~</span><span class="sxs-lookup"><span data-stu-id="a0190-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="a0190-162">檔案傳輸篩選</span><span class="sxs-lookup"><span data-stu-id="a0190-162">File Transfer Filtering</span></span>

<span data-ttu-id="a0190-163">篩選轉移篩選會影響立即訊息和會議。</span><span class="sxs-lookup"><span data-stu-id="a0190-163">Filter transfer filtering affects both instant messages and conferences.</span></span> <span data-ttu-id="a0190-164">在會議中，這些設定會影響 Office Live Meeting 2007 用戶端和多媒體播放功能中的講義功能。</span><span class="sxs-lookup"><span data-stu-id="a0190-164">For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a0190-165">Lync Server 也提供檔案傳輸設定選項。</span><span class="sxs-lookup"><span data-stu-id="a0190-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="a0190-166">除了 Lync Server 中提供的用戶端控制項之外，還提供此伺服器端選項。</span><span class="sxs-lookup"><span data-stu-id="a0190-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="a0190-167">當您使用 Office Live Meeting 2007 用戶端中的講義功能，以及適用于所有檔案類型的多媒體播放功能時，您可以在立即訊息交談期間篩選檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="a0190-167">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types.</span></span> <span data-ttu-id="a0190-168">您可以設定下列選項來控制檔案傳輸：</span><span class="sxs-lookup"><span data-stu-id="a0190-168">You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="a0190-169">**[啟用檔案篩選**   ]：此選項可為全域部署或您選取的網站啟用檔案篩選。</span><span class="sxs-lookup"><span data-stu-id="a0190-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="a0190-170">當您啟用檔案篩選器時，您可以在 [檔案**傳輸**] 中選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="a0190-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="a0190-171">**封鎖特定檔案類型**   ：指定要封鎖的檔副檔名清單，以指定哪些檔案傳輸要求會受到伺服器篩選。</span><span class="sxs-lookup"><span data-stu-id="a0190-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="a0190-172">清單中的專案可以包含所有標準字元，但不能包含通配字元\*（）。</span><span class="sxs-lookup"><span data-stu-id="a0190-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="a0190-173">在 Office Live Meeting 2007 用戶端中，講義功能已啟用，但無法上傳或下載具有此副檔名的任何檔案。</span><span class="sxs-lookup"><span data-stu-id="a0190-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="a0190-174">如果您在 [ **Url 篩選**] 索引標籤上所列的 url 篩選的設定中選取 [**封鎖含檔案副檔名的 url** ] 核取方塊，url 篩選就會使用相同的清單來封鎖包含這些副檔名的作用中超連結。</span><span class="sxs-lookup"><span data-stu-id="a0190-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="a0190-175">若要選擇要封鎖的檔案類型，請按一下 [**選取**]，然後在 [**選取檔案類型**] 中，將檔案類型副檔名新增到 [選取的**檔案類型副檔名**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="a0190-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="a0190-176">**[封鎖所有**   伺服器]：除去所有包含檔案傳輸要求的立即訊息，並傳回錯誤訊息給要求的寄件者。</span><span class="sxs-lookup"><span data-stu-id="a0190-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="a0190-177">Office Live Meeting 2007 用戶端中的 [講義] 功能已停用。</span><span class="sxs-lookup"><span data-stu-id="a0190-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="a0190-178">檔案延伸的篩選只能是標準的檔案名。</span><span class="sxs-lookup"><span data-stu-id="a0190-178">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="a0190-179">篩選可能無法搭配內嵌在其他名稱中的副檔名。</span><span class="sxs-lookup"><span data-stu-id="a0190-179">Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a0190-180">本節內容</span><span class="sxs-lookup"><span data-stu-id="a0190-180">In This Section</span></span>

  - [<span data-ttu-id="a0190-181">在 Lync Server 2013 中修改預設的檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="a0190-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="a0190-182">針對特定網站在 Lync Server 2013 中建立新的檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="a0190-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="a0190-183">在 Lync Server 2013 中修改預設的 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="a0190-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="a0190-184">在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結</span><span class="sxs-lookup"><span data-stu-id="a0190-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0190-185">請參閱</span><span class="sxs-lookup"><span data-stu-id="a0190-185">See Also</span></span>


[<span data-ttu-id="a0190-186">在 Lync Server 2013 中管理 IM 及顯示狀態設定</span><span class="sxs-lookup"><span data-stu-id="a0190-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

