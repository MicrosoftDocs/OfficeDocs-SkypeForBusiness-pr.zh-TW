---
title: 設定 Lync Server 2013 使用 Microsoft Exchange Server 2013 封存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a7f331cfa79472db187f30b626baad9655f2a7b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="b9403-102">設定 Microsoft Lync Server 2013 使用 Microsoft Exchange Server 2013 封存</span><span class="sxs-lookup"><span data-stu-id="b9403-102">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9403-103">_**上次修改主題：** 2014年-06-24_</span><span class="sxs-lookup"><span data-stu-id="b9403-103">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="b9403-104">Microsoft Lync Server 2013 可讓系統管理員選擇讓立即訊息和 Web 會議記錄封存至使用者的 Microsoft Exchange Server 2013 信箱，而不是 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="b9403-104">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="b9403-105">若您啟用了此選項，系統就會將記錄寫入使用者信箱的「清理」資料夾。</span><span class="sxs-lookup"><span data-stu-id="b9403-105">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="b9403-106">「清理」資料夾是「可復原項目」資料夾中的隱藏資料夾。</span><span class="sxs-lookup"><span data-stu-id="b9403-106">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="b9403-107">雖然使用者看不到這個資料夾、 資料夾由 Exchange 搜尋引擎編製索引，而且可以找到使用 Exchange 信箱搜尋和/或 Microsoft SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b9403-107">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="b9403-108">因為 Exchange 就地保留功能 （負責封存電子郵件和其他 Exchange 通訊） 所使用的相同資料夾中儲存的資訊，系統管理員可以使用單一的工具來搜尋所有電子通訊封存使用者。</span><span class="sxs-lookup"><span data-stu-id="b9403-108">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b9403-109">若要完全停用封存的 Lync 交談，您必須也停用 Lync 交談歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="b9403-109">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="b9403-110">如需詳細資訊，請參閱下列主題：<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">管理 Lync Server 2013 中的內部和外部通訊的封存</A>、 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-csclientpolicy</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-csclientpolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="b9403-110">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="b9403-111">若要封存至 Exchange 2013 的記錄您必須首先設定兩部伺服器之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="b9403-111">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="b9403-112">伺服器對伺服器驗證已經準備就緒之後您可以再執行 Microsoft Lync Server 2013 （請注意，根據您的安裝和設定，您可能不需要完成這些工作的所有） 中的下列工作：</span><span class="sxs-lookup"><span data-stu-id="b9403-112">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="b9403-113">啟用 Exchange 封存藉由修改 Lync Server 封存組態設定。</span><span class="sxs-lookup"><span data-stu-id="b9403-113">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="b9403-114">所有部署都必須進行此步驟。</span><span class="sxs-lookup"><span data-stu-id="b9403-114">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="b9403-115">針對使用者的內部及/或外部通訊，啟用封存。</span><span class="sxs-lookup"><span data-stu-id="b9403-115">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="b9403-116">所有部署都必須進行此步驟。</span><span class="sxs-lookup"><span data-stu-id="b9403-116">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="b9403-117">針對每個使用者設定 ExchangeArchivingPolicy 屬性。</span><span class="sxs-lookup"><span data-stu-id="b9403-117">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="b9403-118">此步驟只需要在 Lync Server 和 Exchange 位於不同樹系中。</span><span class="sxs-lookup"><span data-stu-id="b9403-118">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="b9403-119">步驟 1： 啟用 Exchange 封存</span><span class="sxs-lookup"><span data-stu-id="b9403-119">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="b9403-120">使用封存組態設定主要管理 Lync Server 中的封存。</span><span class="sxs-lookup"><span data-stu-id="b9403-120">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="b9403-121">當您安裝 Lync Server 2013 會自動獲得這些設定的單一、 全域集合。</span><span class="sxs-lookup"><span data-stu-id="b9403-121">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="b9403-122">（系統管理員可以選擇性地建立新的封存設定集合在網站範圍）。根據預設，全域設定中，在未啟用封存也不 Exchange 封存啟用這些設定。</span><span class="sxs-lookup"><span data-stu-id="b9403-122">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="b9403-123">若要使用 Exchange 封存系統管理員必須設定 EnableArchiving 和 EnableExchangeArchiving 屬性在這些組態設定。</span><span class="sxs-lookup"><span data-stu-id="b9403-123">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="b9403-124">EnableArchiving 屬性可設定為下列三個可能值之一：</span><span class="sxs-lookup"><span data-stu-id="b9403-124">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="b9403-125">**無**。</span><span class="sxs-lookup"><span data-stu-id="b9403-125">**None**.</span></span> <span data-ttu-id="b9403-126">已停用封存。</span><span class="sxs-lookup"><span data-stu-id="b9403-126">Archiving is disabled.</span></span> <span data-ttu-id="b9403-127">這是預設值。</span><span class="sxs-lookup"><span data-stu-id="b9403-127">This is the default value.</span></span> <span data-ttu-id="b9403-128">如果 EnableArchiving 設為 None，然後執行任何動作將會封存的 Lync Server 封存資料庫中的任一種或 Exchange 2013 中。</span><span class="sxs-lookup"><span data-stu-id="b9403-128">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="b9403-129">**ImOnly**。</span><span class="sxs-lookup"><span data-stu-id="b9403-129">**ImOnly**.</span></span> <span data-ttu-id="b9403-130">僅限立即訊息記錄會封存。</span><span class="sxs-lookup"><span data-stu-id="b9403-130">Only instant message transcripts are archived.</span></span> <span data-ttu-id="b9403-131">如果已啟用 Exchange 封存這些記錄會封存在 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="b9403-131">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="b9403-132">如果 Exchange 封存已停用這些記錄會封存至 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="b9403-132">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="b9403-133">**ImAndWebConf**。</span><span class="sxs-lookup"><span data-stu-id="b9403-133">**ImAndWebConf**.</span></span> <span data-ttu-id="b9403-134">已封存立即訊息記錄和 Web 會議記錄。</span><span class="sxs-lookup"><span data-stu-id="b9403-134">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="b9403-135">如果已啟用 Exchange 封存這些記錄會封存在 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="b9403-135">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="b9403-136">如果 Exchange 封存已停用這些記錄會封存至 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="b9403-136">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="b9403-137">EnableExchangeArchiving 屬性是布林值： 設定為 True ($True) 來啟用 Exchange 封存或設定 EnableExchangeArchiving EnableExchangeArchiving 設為 False ($False) 若要停用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="b9403-137">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="b9403-138">例如，此命令啟用封存的立即訊息的記錄，並也可讓 Exchange 封存：</span><span class="sxs-lookup"><span data-stu-id="b9403-138">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="b9403-139">若要停用 Exchange 封存，請使用類似下列項目，可啟用立即訊息封存，但會停用封存至 Exchange 命令 （也就是說，記錄會封存至 Lync Server）：</span><span class="sxs-lookup"><span data-stu-id="b9403-139">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="b9403-140">如果 EnableArchiving 屬性設為 [無然後 Lync 伺服器將不封存立即訊息和 Web 會議記錄所有。</span><span class="sxs-lookup"><span data-stu-id="b9403-140">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="b9403-141">在這種情況下，伺服器會忽略 EnableExchangeArchiving 所設定的值。</span><span class="sxs-lookup"><span data-stu-id="b9403-141">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="b9403-142">Exchange 封存也可啟用 （或已停用） 使用 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="b9403-142">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="b9403-143">若要執行這項作業，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="b9403-143">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="b9403-144">在控制台中，按一下 [監控和封存]\*\*\*\*，然後按一下 [封存組態]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9403-144">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="b9403-145">在 [封存組態]\*\*\*\* 索引標籤中，按兩下要修改的封存設定集合 (例如，[全域]\*\*\*\* 集合)。</span><span class="sxs-lookup"><span data-stu-id="b9403-145">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="b9403-146">在 [編輯封存設定]\*\*\*\* 窗格中，按一下 [封存設定]\*\*\*\* 下拉式清單，然後選取 [封存 IM 工作階段]\*\*\*\* (若只要封存立即訊息工作階段) 或 [封存 IM 和 Web 會議工作階段]\*\*\*\* (若要封存立即訊息和 Web 會議工作階段)。</span><span class="sxs-lookup"><span data-stu-id="b9403-146">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="b9403-147">選擇之後要封存的項目，選取 [ **Exchange Server 整合**] 核取方塊以啟用 Exchange 封存]。</span><span class="sxs-lookup"><span data-stu-id="b9403-147">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="b9403-148">若要停用 Exchange 封存，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b9403-148">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9403-149">若 [封存設定]<STRONG></STRONG> 是設為 [停用封存]<STRONG></STRONG>，就無法使用 [Exchange 伺服器整合]<STRONG></STRONG> 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b9403-149">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="b9403-150">您必須啟用封存的第一個，然後啟用 [Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="b9403-150">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="b9403-151">如果 Lync Server 2013 和 Exchange 2013 都位於相同的樹系，然後針對個別使用者封存 （或是至少具有電子郵件的使用者帳戶在 Exchange 2013） 的管理方式使用 Exchange 就地保留原則。</span><span class="sxs-lookup"><span data-stu-id="b9403-151">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="b9403-152">如果您有位於舊版的 Exchange 然後封存這些使用者的使用者將受使用 Lync Server 封存原則。</span><span class="sxs-lookup"><span data-stu-id="b9403-152">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="b9403-153">請注意，只具有 Exchange 2013 的帳戶的使用者可能會有封存至 Exchange 其 Lync 文稿。</span><span class="sxs-lookup"><span data-stu-id="b9403-153">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="b9403-154">如果 Lync Server 2013 和 Exchange 2013 都位於不同樹系，然後針對個別使用者封存的管理方式設定 ExchangeArchivingPolicy 屬性的每個個別的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9403-154">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="b9403-155">請參閱「步驟 3」以了解詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b9403-155">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="b9403-156">步驟 2：啟用內部及/或外部通訊的封存</span><span class="sxs-lookup"><span data-stu-id="b9403-156">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="b9403-157">已啟用封存 （及 Exchange 封存後） 然後您必須修改適當的封存原則，以確保已實際上封存的使用者工作階段。</span><span class="sxs-lookup"><span data-stu-id="b9403-157">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="b9403-158">請注意，只啟用 [封存 (步驟 1) 不會導致 Lync Server 以開始封存立即訊息和 Web 會議記錄。</span><span class="sxs-lookup"><span data-stu-id="b9403-158">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="b9403-159">相反地，您必須使用封存原則以啟用內部及/或外部封存。</span><span class="sxs-lookup"><span data-stu-id="b9403-159">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="b9403-160">當您安裝 Lync Server 2013 還安裝單一時，全域封存原則包含兩個屬性：</span><span class="sxs-lookup"><span data-stu-id="b9403-160">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="b9403-p119">**ArchiveInternal**，若設為 True ($True) 表示會封存內部通訊工作階段 (僅涉及組織中具備 Active Directory 帳戶之使用者的工作階段)。</span><span class="sxs-lookup"><span data-stu-id="b9403-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="b9403-p120">**ArchiveExternal**，若設為 True ($True) 表示會封存內部通訊工作階段 (涉及組織中至少有一名具備 Active Directory 帳戶之使用者的工作階段)。</span><span class="sxs-lookup"><span data-stu-id="b9403-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="b9403-165">根據預設，這兩個選項值都會設為 False，亦即不論內部或外部通訊工作階段都不會受到封存。</span><span class="sxs-lookup"><span data-stu-id="b9403-165">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="b9403-166">若要修改全域原則，您可以使用 Lync Server 管理命令介面和 Set-csarchivingpolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b9403-166">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="b9403-167">此命令可啟用內部和外部通訊工作階段的封存：</span><span class="sxs-lookup"><span data-stu-id="b9403-167">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="b9403-p122">您也可以在網站範圍或個別使用者範圍，使用 New-CsArchivingPolicy 來建立新的原則。例如，此命令會建立名為 RedmondArchivingPolicy 的新個別使用者封存原則：</span><span class="sxs-lookup"><span data-stu-id="b9403-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="b9403-p123">若您要建立個別使用者的原則，您就需要將該原則指派給適當的使用者。例如：</span><span class="sxs-lookup"><span data-stu-id="b9403-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="b9403-172">封存原則也可以使用 Lync Server Control Panel 管理。</span><span class="sxs-lookup"><span data-stu-id="b9403-172">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="b9403-173">在控制台中，按一下 [監控和封存]\*\*\*\*，然後按一下 [封存原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9403-173">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="b9403-174">若要修改現有的原則，按兩下原則 (例如：全域)，然後在 [編輯封存原則]\*\*\*\* 窗格中，視需要選取或清除 [封存內部通訊]\*\*\*\* 和 [封存外部通訊]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b9403-174">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="b9403-175">若要建立新的封存原則，按一下 [**新增**]，然後選取**網站原則**或**使用者原則**。</span><span class="sxs-lookup"><span data-stu-id="b9403-175">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="b9403-176">若您建立新的使用者原則，接著就必須存取適當的使用者帳戶 (從 [使用者]\*\*\*\* 索引標籤)，然後再將新的原則指派給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="b9403-176">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="b9403-177">步驟 3：設定 ExchangeArchivingPolicy 屬性</span><span class="sxs-lookup"><span data-stu-id="b9403-177">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="b9403-178">如果 Lync Server 2013 和 Exchange 2013 位於不同樹系中則不足夠只啟用 Exchange 封存中的封存組態設定;不會造成立即訊息和 Web 會議記錄在 Exchange 封存中。</span><span class="sxs-lookup"><span data-stu-id="b9403-178">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="b9403-179">相反地，您也必須在每個相關的 Lync Server 使用者帳戶上設定 ExchangeArchivingPolicy 屬性。</span><span class="sxs-lookup"><span data-stu-id="b9403-179">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="b9403-180">您可將此屬性設為下列四個可能值之一：</span><span class="sxs-lookup"><span data-stu-id="b9403-180">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="b9403-181">未初始化。</span><span class="sxs-lookup"><span data-stu-id="b9403-181">Uninitialized.</span></span> <span data-ttu-id="b9403-182">會指出，封存會根據使用者的 Exchange 信箱; 設定為 「 就地保留設定如果原有範圍暫止不上已啟用使用者的信箱則使用者將會有他/她訊息和 Web 會議記錄封存的 Lync 伺服器中。</span><span class="sxs-lookup"><span data-stu-id="b9403-182">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="b9403-183">**為 UseLyncArchivingPolicy**。</span><span class="sxs-lookup"><span data-stu-id="b9403-183">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="b9403-184">會指出該使用者的立即訊息和 Web 會議記錄應該封存 Lync Server，而非 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="b9403-184">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="b9403-185">**NoArchiving**。</span><span class="sxs-lookup"><span data-stu-id="b9403-185">**NoArchiving**.</span></span> <span data-ttu-id="b9403-186">會指出該使用者的立即訊息和 Web 會議記錄應該不會封存所有。</span><span class="sxs-lookup"><span data-stu-id="b9403-186">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="b9403-187">請注意，此設定會覆寫任何 Lync Server 封存原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b9403-187">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="b9403-188">**ArchivingToExchange**。</span><span class="sxs-lookup"><span data-stu-id="b9403-188">**ArchivingToExchange**.</span></span> <span data-ttu-id="b9403-189">會指出使用者的立即訊息和 Web 會議記錄應該封存至 Exchange 就地保留設定不論有 （或不具有） 已指派給使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="b9403-189">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="b9403-190">例如，若要設定的使用者帳戶，以便立即訊息和 Web 會議記錄一律封存至 Exchange，您可以使用類似從 Lync Server 管理命令介面命令：</span><span class="sxs-lookup"><span data-stu-id="b9403-190">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="b9403-191">若您想針對群組使用者 (例如，所有位於特定登錄器集區的使用者) 設定相同的封存原則，可使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="b9403-191">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="b9403-192">請注意，您必須使用 Lync Server 管理命令介面 （和 Windows PowerShell），才能設定 ExchangeArchivingPolicy 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="b9403-192">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="b9403-193">此屬性不會公開給 Lync Server Control Panel 中的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="b9403-193">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="b9403-194">若您要檢視已指派特定封存原則之所有使用者的清單，您就可以使用類似下列的命令，即可傳回已將 ExchangeArchivingPolicy 屬性設為 Uninitialized 之所有使用者的 Active Directory 顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="b9403-194">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="b9403-195">同樣地，此命令會傳回已將 ExchangeArchivingPolicy 屬性設為 UseLyncArchivingPolicy 之使用者的顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="b9403-195">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

