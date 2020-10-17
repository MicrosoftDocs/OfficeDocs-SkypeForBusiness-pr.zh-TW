---
title: 設定立即訊息 (IM) 的檔案傳送和 URL 篩選
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bad134c770300820bd4fb6bd2d72e648b5f34777
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517510"
---
# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="379a1-102">在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="379a1-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="379a1-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="379a1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="379a1-104">智慧 IM 篩選工具可協助保護您的 Lync Server 2013 部署，使其免受最常見的病毒形式傳播，以降低使用者體驗的程度。</span><span class="sxs-lookup"><span data-stu-id="379a1-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="379a1-105">使用智慧型 IM 篩選器可以設定篩選器，以封鎖來自企業防火牆外部之不明端點的來路不明或潛在有害的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="379a1-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="379a1-106">您可以指定用來判斷所應封鎖項目的條件，藉以設定篩選器，例如立即訊息中包含具有特定首碼的超連結與具有特定副檔名的檔案。</span><span class="sxs-lookup"><span data-stu-id="379a1-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="379a1-107">智慧型 IM 篩選器提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="379a1-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="379a1-108">增強型 URL 篩選。</span><span class="sxs-lookup"><span data-stu-id="379a1-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="379a1-109">增強型檔案傳輸篩選。</span><span class="sxs-lookup"><span data-stu-id="379a1-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="379a1-110">智慧型 IM 篩選器的設定包括：</span><span class="sxs-lookup"><span data-stu-id="379a1-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="379a1-111">設定 URL 篩選。</span><span class="sxs-lookup"><span data-stu-id="379a1-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="379a1-112">設定檔案傳輸篩選。</span><span class="sxs-lookup"><span data-stu-id="379a1-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="379a1-113">篩選選項套用至立即訊息的方式</span><span class="sxs-lookup"><span data-stu-id="379a1-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="379a1-114">在您部署智慧 IM 郵件篩選工具之前，您必須瞭解如何套用篩選選項，因為郵件是從一部 Lync Server 2013 伺服器路由傳送到另一個。</span><span class="sxs-lookup"><span data-stu-id="379a1-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="379a1-115">無論伺服器位於單一組織內，或是涵蓋多個組織，套用這些篩選選項的方式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="379a1-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="379a1-116">這種一致性適用於自訂通知和警告文字插入訊息及跨伺服器傳送的方式。</span><span class="sxs-lookup"><span data-stu-id="379a1-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="379a1-117">立即訊息篩選器會增加訊息中處理 URL 所需的 CPU 資源量。</span><span class="sxs-lookup"><span data-stu-id="379a1-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="379a1-118">此增加的 CPU 需求也會影響 Lync Server 的效能。</span><span class="sxs-lookup"><span data-stu-id="379a1-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="379a1-119">使用 [Lync Server 控制台] 中 [ **IM 和目前狀態**] 群組中的 [ **URL 篩選**] 頁面，您可以封鎖部分或所有超連結或設定警告。</span><span class="sxs-lookup"><span data-stu-id="379a1-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="379a1-120">當您選擇 [超連結首碼]\*\*\*\* 選項 [傳送警告訊息]\*\*\*\* 時，即會在包含超連結的立即訊息開頭處插入警告。</span><span class="sxs-lookup"><span data-stu-id="379a1-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="379a1-121">當立即訊息從一部伺服器傳送到另一部伺服器時，會套用下列一般方針：</span><span class="sxs-lookup"><span data-stu-id="379a1-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="379a1-p105">如果伺服器封鎖立即訊息 (由於您在 **[URL 篩選器]** 頁面上選取了 **[封鎖含有副檔名的 URL]** 核取方塊，或選擇了 **[超連結首碼]** 選項 **[封鎖超連結]**)，則會將錯誤訊息傳回至用戶端。後續的伺服器將不會收到此立即訊息。</span><span class="sxs-lookup"><span data-stu-id="379a1-p105">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client. Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="379a1-p106">如果伺服器 (Server1) 將警告新增至包含作用中超連結的立即訊息中，收到此立即訊息的後續伺服器 (Server2) 仍可以依據該立即訊息中出現的這個作用中超連結來採取不同的動作，並封鎖該立即訊息或新增警告。如果 Server2 設定為僅新增此 URL 的警告，便會移除之前由 Server1 新增的警告，而在 Server2 上所設定的警告將會新增至該立即訊息的開頭處。</span><span class="sxs-lookup"><span data-stu-id="379a1-p106">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning. If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="379a1-126">如果您是在混合環境中執行 Lync Server 2013，則使用智慧 IM 篩選應用程式所需的即時通訊伺服器2005（含 SP1）是最低的版本。</span><span class="sxs-lookup"><span data-stu-id="379a1-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="379a1-127">不具 SP1 的 Live Communications Server 2005 不支援智慧型 IM 篩選器。</span><span class="sxs-lookup"><span data-stu-id="379a1-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="379a1-128">URL 篩選</span><span class="sxs-lookup"><span data-stu-id="379a1-128">URL Filtering</span></span>

<span data-ttu-id="379a1-p108">URL 可根據其超連結首碼受到篩選。以下是有效首碼的範例：</span><span class="sxs-lookup"><span data-stu-id="379a1-p108">URLs are filtered according to their hyperlink prefix. The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="379a1-131">www \* 。</span><span class="sxs-lookup"><span data-stu-id="379a1-131">www\*.</span></span>

  - <span data-ttu-id="379a1-132">Ftp。</span><span class="sxs-lookup"><span data-stu-id="379a1-132">ftp.</span></span>

  - <span data-ttu-id="379a1-133">HTTP.sys</span><span class="sxs-lookup"><span data-stu-id="379a1-133">http:</span></span>

<span data-ttu-id="379a1-p109">如果您未設定立即訊息篩選器來執行任何 URL 篩選，則立即訊息中所包含的所有 URL 都會以原狀通過伺服器。如果您設定立即訊息篩選器來執行 URL 篩選，則立即訊息中的 URL 都會根據您在 **[編輯 URL 篩選器]** 或 **[新增 URL 篩選器]** 對話方塊中所選取的選項受到篩選。</span><span class="sxs-lookup"><span data-stu-id="379a1-p109">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server. If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="379a1-136">**啟用 URL 篩選器**    此選項會為全域部署或您所選取的網站啟用 URL 篩選。</span><span class="sxs-lookup"><span data-stu-id="379a1-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="379a1-137">**使用副檔名**     封鎖 URLs立即訊息篩選器會封鎖任何使用中的內部網路或網際網路 URL，其中包含副檔名列于 [**編輯檔案篩選**] 對話方塊的 [**檔案類型副檔名**] 底下的副檔名。</span><span class="sxs-lookup"><span data-stu-id="379a1-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="379a1-138">當封鎖 URL 時，系統會向寄件者顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="379a1-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="379a1-139">選取此選項時，此選項會優先于所有其他篩選選項，以 [副檔名] 副檔名為 [ **封鎖**] 的任何副檔名。</span><span class="sxs-lookup"><span data-stu-id="379a1-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="379a1-p111">副檔名的篩選僅限於標準的檔案名稱。內嵌在其他名稱中的副檔名可能篩選不出來。</span><span class="sxs-lookup"><span data-stu-id="379a1-p111">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="379a1-142">若要設定如何處理立即訊息交談中的超連結，請選取下列位於 [超連結首碼]\*\*\*\* 下方的其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="379a1-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="379a1-143">不**篩選**    在郵件中 URLs 會透過伺服器傳送。</span><span class="sxs-lookup"><span data-stu-id="379a1-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="379a1-144">當您選擇此選項時，會出現 [ **允許] 消息** 框。</span><span class="sxs-lookup"><span data-stu-id="379a1-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="379a1-145">在 [ **允許消息** ] 方塊中，指定您要在每個包含超連結的立即訊息開頭插入的通知。</span><span class="sxs-lookup"><span data-stu-id="379a1-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="379a1-146">此通知包含的字元不得超過65535個。</span><span class="sxs-lookup"><span data-stu-id="379a1-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="379a1-147">**封鎖超連結**    傳送包含作用中超連結的立即訊息會由 Lync Server 封鎖，並對寄件者顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="379a1-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="379a1-148">**傳送警告訊息**    Lync Server 允許立即訊息中的使用中超連結，但包含警告。</span><span class="sxs-lookup"><span data-stu-id="379a1-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="379a1-149">選擇此選項時，會出現 [警告訊息]\*\*\*\* 方塊。</span><span class="sxs-lookup"><span data-stu-id="379a1-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="379a1-150">在 [警告訊息]\*\*\*\* 方塊中，您必須輸入要在包含有效超連結的立即訊息中隨附的警告。</span><span class="sxs-lookup"><span data-stu-id="379a1-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="379a1-151">例如，此警告可指出點選不明連結的潛在風險，或提及您組織的相關原則與需求。</span><span class="sxs-lookup"><span data-stu-id="379a1-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="379a1-152">此警告最多可包含 65535 個字元。</span><span class="sxs-lookup"><span data-stu-id="379a1-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="379a1-153">選取 **[封鎖超連結]** 或 **[傳送警告訊息]** 時，可用的選項如下：</span><span class="sxs-lookup"><span data-stu-id="379a1-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="379a1-154">**排除本機內部網路超連結**    立即訊息篩選只會封鎖網際網路 URLs。</span><span class="sxs-lookup"><span data-stu-id="379a1-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="379a1-155">內部網路內位置的 URLs 會透過伺服器進行未修改的傳遞。</span><span class="sxs-lookup"><span data-stu-id="379a1-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="379a1-156">不過，內部網路 URLs 執行 Lync Server 的個別伺服器，取決於哪些類型的本機網站會被視為其內部網路區域的一部分。</span><span class="sxs-lookup"><span data-stu-id="379a1-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="379a1-157">若要檢查伺服器的內部網路區域設定，請參閱在 [Lync server 2013 中修改預設 URL 篩選器](lync-server-2013-modify-the-default-url-filter.md)中的「在 Internet Explorer 中設定您的內部網路設定」程式。</span><span class="sxs-lookup"><span data-stu-id="379a1-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="379a1-158">**篩選這些超連結首碼**    若要選擇要封鎖的首碼，請按一下 [**選取**]，然後在 [**選取超連結首碼**] 中，將首碼新增至 [**超連結首碼**] 清單。</span><span class="sxs-lookup"><span data-stu-id="379a1-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="379a1-159">除了 **href** 以外的所有首碼都必須以點或冒號結尾，或是以星號接著點為結尾。</span><span class="sxs-lookup"><span data-stu-id="379a1-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="379a1-160">有效的首碼可以包含有效 URL 字元集合中的任何字元，星號 (\*) 除外。</span><span class="sxs-lookup"><span data-stu-id="379a1-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="379a1-161">有效的 URL 字元組為： \# \* +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ \_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~</span><span class="sxs-lookup"><span data-stu-id="379a1-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="379a1-162">檔案傳輸篩選</span><span class="sxs-lookup"><span data-stu-id="379a1-162">File Transfer Filtering</span></span>

<span data-ttu-id="379a1-p116">檔案傳輸篩選對立即訊息與會議都會有影響。對於會議，這些設定會影響 Office Live Meeting 2007 用戶端中的講義功能及多媒體播放功能。</span><span class="sxs-lookup"><span data-stu-id="379a1-p116">Filter transfer filtering affects both instant messages and conferences. For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="379a1-165">Lync Server 也提供檔案傳輸設定選項。</span><span class="sxs-lookup"><span data-stu-id="379a1-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="379a1-166">除了 Lync Server 中可用的用戶端控制項之外，也提供此伺服器端選項。</span><span class="sxs-lookup"><span data-stu-id="379a1-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="379a1-p118">當您在 Office Live Meeting 2007 用戶端中使用講義功能，或使用各種檔案類型的多媒體播放功能時，您可以篩選立即訊息交談期間的檔案傳輸。您可以設定下列選項以控制檔案傳輸：</span><span class="sxs-lookup"><span data-stu-id="379a1-p118">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types. You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="379a1-169">**啟用檔案篩選器**    此選項會為全域部署或您所選取的網站啟用檔篩選。</span><span class="sxs-lookup"><span data-stu-id="379a1-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="379a1-170">當您啟用檔案篩選器時，您可以在 **[檔案傳輸]** 中選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="379a1-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="379a1-171">**封鎖特定檔案類型**    您可以指定要封鎖的副檔名清單，以指定由伺服器篩選的檔案傳輸要求。</span><span class="sxs-lookup"><span data-stu-id="379a1-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="379a1-172">清單中的專案可以包含所有標準字元，但不能包含萬用字元 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="379a1-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="379a1-173">在 Office Live Meeting 2007 用戶端中，講義功能已啟用，但無法上傳或下載任何具有此副檔名的檔案。</span><span class="sxs-lookup"><span data-stu-id="379a1-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="379a1-174">如果您選取 [ **Url 篩選**] 索引標籤上所列之 url 篩選器之設定上的 [**封鎖 URLs 搭配副檔名**] 核取方塊，則 url 篩選會使用此相同清單來封鎖包含這些副檔名的使用中超連結。</span><span class="sxs-lookup"><span data-stu-id="379a1-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="379a1-175">若要選擇要封鎖的檔案類型，請按一下 [ **選取**]，然後在 [ **選取檔案類型**] 中，將檔案類型副檔名新增至 [選取的 **檔案類型副檔名** ] 清單。</span><span class="sxs-lookup"><span data-stu-id="379a1-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="379a1-176">**全部封鎖**    伺服器會丟棄所有包含檔案傳輸要求的立即訊息，並將錯誤訊息傳回給要求的寄件者。</span><span class="sxs-lookup"><span data-stu-id="379a1-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="379a1-177">Office Live Meeting 2007 用戶端中的講義功能已停用。</span><span class="sxs-lookup"><span data-stu-id="379a1-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="379a1-p121">副檔名的篩選僅限於標準的檔案名稱。內嵌在其他名稱中的副檔名可能篩選不出來。</span><span class="sxs-lookup"><span data-stu-id="379a1-p121">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="379a1-180">本節內容</span><span class="sxs-lookup"><span data-stu-id="379a1-180">In This Section</span></span>

  - [<span data-ttu-id="379a1-181">在 Lync Server 2013 中修改預設檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="379a1-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="379a1-182">在 Lync Server 2013 中為特定網站建立新的檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="379a1-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="379a1-183">在 Lync Server 2013 中修改預設 URL 篩選器</span><span class="sxs-lookup"><span data-stu-id="379a1-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="379a1-184">在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結</span><span class="sxs-lookup"><span data-stu-id="379a1-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="379a1-185">另請參閱</span><span class="sxs-lookup"><span data-stu-id="379a1-185">See Also</span></span>


[<span data-ttu-id="379a1-186">在 Lync Server 2013 中管理 IM 及顯示狀態設定</span><span class="sxs-lookup"><span data-stu-id="379a1-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

