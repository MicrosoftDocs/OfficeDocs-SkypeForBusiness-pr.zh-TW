---
title: 設定商務用 Skype Server 以使用 Exchange Server 封存
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 摘要：設定 Exchange Server 2016 或 Exchange Server 2013 和商務用 Skype Server 的 IM 記錄。
ms.openlocfilehash: 43a57fc227f7fc0dbcb33b2ecb4808f3e9762ad6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120312"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a><span data-ttu-id="2d600-103">設定商務用 Skype Server 以使用 Exchange Server 封存</span><span class="sxs-lookup"><span data-stu-id="2d600-103">Configure Skype for Business Server to use Exchange Server archiving</span></span>

<span data-ttu-id="2d600-104">**摘要：** 設定 Exchange Server 2016 或 Exchange Server 2013 和商務用 Skype Server 的 IM 記錄。</span><span class="sxs-lookup"><span data-stu-id="2d600-104">**Summary:** Configure IM transcripts for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>

<span data-ttu-id="2d600-105">商務用 Skype 伺服器讓管理員可以選擇將立即訊息和 Web 會議記錄封存到使用者的 Exchange Server 2016 或 Exchange Server 2013 信箱，而不是 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="2d600-105">Skype for Business Server gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Exchange Server 2016 or Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="2d600-106">若您啟用了此選項，系統就會將記錄寫入使用者信箱的「清理」資料夾。</span><span class="sxs-lookup"><span data-stu-id="2d600-106">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="2d600-107">「清理」資料夾是「可復原項目」資料夾中的隱藏資料夾。</span><span class="sxs-lookup"><span data-stu-id="2d600-107">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="2d600-108">雖然使用者看不到此資料夾，但該資料夾是由 Exchange 搜尋引擎編制索引，而且可以使用 Exchange 信箱搜尋和/或 Microsoft SharePoint Server 2013 來探索。</span><span class="sxs-lookup"><span data-stu-id="2d600-108">Although this folder is not visible to end users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="2d600-109">因為資訊儲存在 Exchange In-Place 保留功能所使用的相同資料夾中 (負責封存電子郵件和其他 Exchange 通訊) ，所以系統管理員可以使用單一工具來搜尋所有為使用者封存的電子通訊。</span><span class="sxs-lookup"><span data-stu-id="2d600-109">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d600-110">若要完全停用交談封存，您也必須停用交談記錄。</span><span class="sxs-lookup"><span data-stu-id="2d600-110">To completely disable conversation archiving, you must also disable conversation history.</span></span> <span data-ttu-id="2d600-111">如需詳細資訊，請參閱下列主題： [管理商務用 Skype Server 中的內部和外部通訊](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications)封存、 [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)和 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2d600-111">For more information, see the following topics: [Managing the Archiving of internal and external communications in Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications), [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps), and [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span>

<span data-ttu-id="2d600-112">若要將記錄封存至 Exchange Server，您必須先設定商務用 Skype Server 與 Exchange Server 之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="2d600-112">In order to archive transcripts to Exchange Server you must begin by configuring server-to-server authentication between Skype for Business Server and Exchange Server.</span></span> <span data-ttu-id="2d600-113">在進行伺服器對伺服器驗證之後，您就可以在商務用 Skype Server 中執行下列工作 (請注意，視您的設定和設定而定，您可能不需要完成下列所有工作) ：</span><span class="sxs-lookup"><span data-stu-id="2d600-113">After server-to-server authentication is in place, you can then carry out the following tasks in Skype for Business Server (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1. <span data-ttu-id="2d600-114">修改商務用 Skype 伺服器封存設定設定，以啟用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-114">Enable Exchange archiving by modifying your Skype for Business Server archiving configuration settings.</span></span> <span data-ttu-id="2d600-115">所有部署都必須進行此步驟。</span><span class="sxs-lookup"><span data-stu-id="2d600-115">This step is required for all deployments.</span></span>

2. <span data-ttu-id="2d600-116">針對使用者的內部及/或外部通訊，啟用封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-116">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="2d600-117">所有部署都必須進行此步驟。</span><span class="sxs-lookup"><span data-stu-id="2d600-117">This step is required for all deployments.</span></span>

3. <span data-ttu-id="2d600-118">針對每個使用者設定 ExchangeArchivingPolicy 屬性。</span><span class="sxs-lookup"><span data-stu-id="2d600-118">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="2d600-119">只有在商務用 Skype Server 和 Exchange Server 位於不同樹系時，才需要此步驟。</span><span class="sxs-lookup"><span data-stu-id="2d600-119">This step is only required if Skype for Business Server and Exchange Server are located in different forests.</span></span>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="2d600-120">步驟1：啟用 Exchange 封存</span><span class="sxs-lookup"><span data-stu-id="2d600-120">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="2d600-121">商務用 Skype Server 中的封存主要是使用封存設定設定來管理。</span><span class="sxs-lookup"><span data-stu-id="2d600-121">Archiving in Skype for Business Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="2d600-122">當您安裝商務用 Skype Server 時，系統會自動提供這些設定的單一全域集合。</span><span class="sxs-lookup"><span data-stu-id="2d600-122">When you install Skype for Business Server you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="2d600-123"> (管理員可以選擇性地在網站範圍建立新的封存設定集合。 ) 依預設，全域設定中不會啟用封存，也不會在這些設定中啟用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-123">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="2d600-124">為了使用 Exchange 封存，管理員必須在這些設定設定中設定 EnableArchiving 和 EnableExchangeArchiving 屬性。</span><span class="sxs-lookup"><span data-stu-id="2d600-124">In order to use Exchange archiving, administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="2d600-125">EnableArchiving 屬性可設定為下列三個可能值之一：</span><span class="sxs-lookup"><span data-stu-id="2d600-125">The EnableArchiving property can be set to one of three possible values:</span></span>

- <span data-ttu-id="2d600-126">**None**。</span><span class="sxs-lookup"><span data-stu-id="2d600-126">**None**.</span></span> <span data-ttu-id="2d600-127">封存已停用。</span><span class="sxs-lookup"><span data-stu-id="2d600-127">Archiving is disabled.</span></span> <span data-ttu-id="2d600-128">這是預設值。</span><span class="sxs-lookup"><span data-stu-id="2d600-128">This is the default value.</span></span> <span data-ttu-id="2d600-129">如果 EnableArchiving 設定為 [無]，則不會在商務用 Skype Server 封存資料庫或 Exchange Server 中封存任何專案。</span><span class="sxs-lookup"><span data-stu-id="2d600-129">If EnableArchiving is set to None then nothing will be archived in either your Skype for Business Server archiving database or in Exchange Server.</span></span>

- <span data-ttu-id="2d600-130">**ImOnly**。</span><span class="sxs-lookup"><span data-stu-id="2d600-130">**ImOnly**.</span></span> <span data-ttu-id="2d600-131">只封存立即訊息記錄。</span><span class="sxs-lookup"><span data-stu-id="2d600-131">Only instant message transcripts are archived.</span></span> <span data-ttu-id="2d600-132">如果啟用 Exchange 封存，這些記錄會在 Exchange Server 中封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-132">If Exchange archiving is enabled, these transcripts will be archived in Exchange Server.</span></span> <span data-ttu-id="2d600-133">如果停用 Exchange 封存，則這些記錄會封存到商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="2d600-133">If Exchange archiving is disabled then these transcripts will be archived to Skype for Business Server.</span></span>

- <span data-ttu-id="2d600-134">**ImAndWebConf**。</span><span class="sxs-lookup"><span data-stu-id="2d600-134">**ImAndWebConf**.</span></span> <span data-ttu-id="2d600-135">立即訊息記錄和 Web 會議記錄皆已封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-135">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="2d600-136">如果啟用 Exchange 封存，這些記錄會在 Exchange Server 中封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-136">If Exchange archiving is enabled these transcripts will be archived in Exchange Server.</span></span> <span data-ttu-id="2d600-137">如果停用 Exchange 封存，則這些記錄會封存到商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="2d600-137">If Exchange archiving is disabled then these transcripts will be archived to Skype for Business Server.</span></span>

<span data-ttu-id="2d600-138">EnableExchangeArchiving 屬性為 Boolean 值：將 EnableExchangeArchiving 設定為 True ($True) 啟用 Exchange 封存，或將 EnableExchangeArchiving 設定為 False ($False) 以停用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-138">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="2d600-139">例如，此命令可啟用立即訊息記錄的封存，也可啟用 Exchange 封存：</span><span class="sxs-lookup"><span data-stu-id="2d600-139">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

<span data-ttu-id="2d600-140">若要停用 Exchange 封存，請使用類似下列的命令，以啟用立即訊息封存，但會停用封存至 Exchange (換句話說，將會封存到商務用 Skype Server) ：</span><span class="sxs-lookup"><span data-stu-id="2d600-140">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Skype for Business Server):</span></span>

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> <span data-ttu-id="2d600-141">如果 EnableArchiving 屬性設定為 [無]，則商務用 Skype 伺服器將不會立即封存立即訊息和 Web 會議記錄。</span><span class="sxs-lookup"><span data-stu-id="2d600-141">If the EnableArchiving property is set to None, then Skype for Business Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="2d600-142">在這種情況下，伺服器會忽略 EnableExchangeArchiving 所設定的值。</span><span class="sxs-lookup"><span data-stu-id="2d600-142">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>

<span data-ttu-id="2d600-143">您也可以 (或停用商務用 Skype 伺服器) 啟用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-143">Exchange archiving can also be enabled (or disabled) by using the Skype for Business Server.</span></span> <span data-ttu-id="2d600-144">若要執行這項作業，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="2d600-144">To do that, complete the following procedure:</span></span>

1. <span data-ttu-id="2d600-145">在控制台中，按一下 [監控和封存]，然後按一下 [封存組態]。</span><span class="sxs-lookup"><span data-stu-id="2d600-145">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2. <span data-ttu-id="2d600-146">在 [封存組態] 索引標籤中，按兩下要修改的封存設定集合 (例如，[全域] 集合)。</span><span class="sxs-lookup"><span data-stu-id="2d600-146">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3. <span data-ttu-id="2d600-147">在 [編輯封存設定] 窗格中，按一下 [封存設定] 下拉式清單，然後選取 [封存 IM 工作階段] (若只要封存立即訊息工作階段) 或 [封存 IM 和 Web 會議工作階段] (若要封存立即訊息和 Web 會議工作階段)。</span><span class="sxs-lookup"><span data-stu-id="2d600-147">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4. <span data-ttu-id="2d600-148">選擇要封存的專案後，請選取 [ **Exchange Server 整合** ] 核取方塊以啟用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-148">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="2d600-149">若要停用 Exchange 封存，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2d600-149">To disable Exchange archiving, clear this checkbox.</span></span>

> [!NOTE]
> <span data-ttu-id="2d600-150">若 [封存設定] 是設為 [停用封存]，就無法使用 [Exchange 伺服器整合] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2d600-150">The **Exchange Server integration** checkbox will not be available if the **Archiving setting** is set to **Disable archiving**.</span></span> <span data-ttu-id="2d600-151">您必須先啟用封存，然後啟用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-151">You must enable archiving first and then enable Exchange archiving.</span></span>

<span data-ttu-id="2d600-152">如果商務用 Skype Server 和 Exchange Server 位於相同樹系中，則個別使用者的封存 (或至少用於在 Exchange Server) 上具有電子郵件帳戶的使用者，都是使用 Exchange In-Place 保留原則來管理。</span><span class="sxs-lookup"><span data-stu-id="2d600-152">If Skype for Business Server and Exchange Server are located in the same forest, then archiving for individual users (or at least for users who have email accounts on Exchange Server) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="2d600-153">如果您有位於舊版 Exchange 的使用者，則會使用商務用 Skype Server 封存原則來管理那些使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-153">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Skype for Business Server archiving policies.</span></span> <span data-ttu-id="2d600-154">請注意，只有在 Exchange Server 2016 或 Exchange Server 2013 上具有帳戶的使用者，才能將其商務用 Skype 記錄封存至 Exchange。</span><span class="sxs-lookup"><span data-stu-id="2d600-154">Note that only users with accounts on Exchange Server 2016 or Exchange Server 2013 can have their Skype for Business transcripts archived to Exchange.</span></span>

<span data-ttu-id="2d600-155">如果商務用 Skype Server 和 Exchange Server 位於不同的樹系中，則會透過設定每個個別使用者帳戶的 ExchangeArchivingPolicy 屬性來管理個別使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-155">If Skype for Business Server and Exchange Server are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="2d600-156">請參閱「步驟 3」以了解詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2d600-156">See Step 3 for more information.</span></span>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="2d600-157">步驟 2：啟用內部及/或外部通訊的封存</span><span class="sxs-lookup"><span data-stu-id="2d600-157">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="2d600-158">在您啟用封存 (和 Exchange 封存) 之後，您必須修改適當的封存原則，以確保實際封存使用者會話。</span><span class="sxs-lookup"><span data-stu-id="2d600-158">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="2d600-159">請注意，只要啟用封存 (步驟 1) 不會導致商務用 Skype 伺服器開始封存立即訊息和 Web 會議記錄。</span><span class="sxs-lookup"><span data-stu-id="2d600-159">Note that simply enabling archiving (Step 1) does not cause Skype for Business Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="2d600-160">相反地，您必須使用封存原則來啟用內部及（或）外部封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-160">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="2d600-161">當您安裝商務用 Skype Server 時，您也會安裝單一的全域封存原則，其中包含兩個屬性：</span><span class="sxs-lookup"><span data-stu-id="2d600-161">When you install Skype for Business Server you also install a single, global archiving policy that contains two properties:</span></span>

- <span data-ttu-id="2d600-p119">**ArchiveInternal**，若設為 True ($True) 表示會封存內部通訊工作階段 (僅涉及組織中具備 Active Directory 帳戶之使用者的工作階段)。</span><span class="sxs-lookup"><span data-stu-id="2d600-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

- <span data-ttu-id="2d600-p120">**ArchiveExternal**，若設為 True ($True) 表示會封存內部通訊工作階段 (涉及組織中至少有一名具備 Active Directory 帳戶之使用者的工作階段)。</span><span class="sxs-lookup"><span data-stu-id="2d600-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="2d600-166">根據預設，這兩個選項值都會設為 False，亦即不論內部或外部通訊工作階段都不會受到封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-166">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="2d600-167">若要修改全域原則，您可以使用商務用 Skype Server 管理命令介面和 Set-CsArchivingPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2d600-167">To modify the global policy, you can use the Skype for Business Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="2d600-168">此命令可啟用內部和外部通訊工作階段的封存：</span><span class="sxs-lookup"><span data-stu-id="2d600-168">This command enables the archiving of both internal and external communication sessions:</span></span>

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

<span data-ttu-id="2d600-p122">您也可以在網站範圍或個別使用者範圍，使用 New-CsArchivingPolicy 來建立新的原則。例如，此命令會建立名為 RedmondArchivingPolicy 的新個別使用者封存原則：</span><span class="sxs-lookup"><span data-stu-id="2d600-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

<span data-ttu-id="2d600-p123">若您要建立個別使用者的原則，您就需要將該原則指派給適當的使用者。例如：</span><span class="sxs-lookup"><span data-stu-id="2d600-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

<span data-ttu-id="2d600-173">您也可以使用商務用 Skype Server 控制台來管理封存原則。</span><span class="sxs-lookup"><span data-stu-id="2d600-173">Archiving policies can also be managed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="2d600-174">在控制台中，按一下 [監控和封存]，然後按一下 [封存原則]。</span><span class="sxs-lookup"><span data-stu-id="2d600-174">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="2d600-175">若要修改現有的原則，按兩下原則 (例如：全域)，然後在 [編輯封存原則] 窗格中，視需要選取或清除 [封存內部通訊] 和 [封存外部通訊] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2d600-175">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="2d600-176">若要建立新的封存原則，請按一下 [ **新增** ]，然後選取 [ **網站原則** ] 或 [ **使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="2d600-176">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="2d600-177">若您建立新的使用者原則，接著就必須存取適當的使用者帳戶 (從 [使用者] 索引標籤)，然後再將新的原則指派給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="2d600-177">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="2d600-178">步驟 3：設定 ExchangeArchivingPolicy 屬性</span><span class="sxs-lookup"><span data-stu-id="2d600-178">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="2d600-179">如果商務用 Skype Server 和 Exchange Server 位於不同的樹系中，則在封存設定設定中只啟用 Exchange 封存是不夠的。這不會導致立即訊息和 Web 會議記錄在 Exchange 中封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-179">If Skype for Business Server and Exchange Server are located in different forests, then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="2d600-180">相反地，您也必須設定每個相關商務用 Skype Server 使用者帳戶的 ExchangeArchivingPolicy 屬性。</span><span class="sxs-lookup"><span data-stu-id="2d600-180">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Skype for Business Server user accounts.</span></span> <span data-ttu-id="2d600-181">您可將此屬性設為下列四個可能值之一：</span><span class="sxs-lookup"><span data-stu-id="2d600-181">This property can be set to one of four possible values:</span></span>

1. <span data-ttu-id="2d600-182">**未初始化**。</span><span class="sxs-lookup"><span data-stu-id="2d600-182">**Uninitialized**.</span></span> <span data-ttu-id="2d600-183">表示封存會根據使用者的 Exchange 信箱所設定的 In-Place 保留設定而定;如果使用者的信箱尚未啟用 In-Place 暫止狀態，使用者會將其郵件和 Web 會議記錄封存在商務用 Skype Server 中。</span><span class="sxs-lookup"><span data-stu-id="2d600-183">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Skype for Business Server.</span></span>

2. <span data-ttu-id="2d600-184">**UseLyncArchivingPolicy**。</span><span class="sxs-lookup"><span data-stu-id="2d600-184">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="2d600-185">表示使用者的立即訊息和 Web 會議記錄應該封存在商務用 Skype Server 中，而不是在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="2d600-185">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Skype for Business Server rather than in Exchange.</span></span>

3. <span data-ttu-id="2d600-186">**NoArchiving**。</span><span class="sxs-lookup"><span data-stu-id="2d600-186">**NoArchiving**.</span></span> <span data-ttu-id="2d600-187">表示使用者的立即訊息和 Web 會議記錄根本不應該封存。</span><span class="sxs-lookup"><span data-stu-id="2d600-187">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="2d600-188">請注意，此設定會覆寫指派給使用者的任何商務用 Skype Server 封存原則。</span><span class="sxs-lookup"><span data-stu-id="2d600-188">Note that this setting overrides any Skype for Business Server archiving policies assigned to the user.</span></span>

4. <span data-ttu-id="2d600-189">**ArchivingToExchange**。</span><span class="sxs-lookup"><span data-stu-id="2d600-189">**ArchivingToExchange**.</span></span> <span data-ttu-id="2d600-190">指出使用者的立即訊息和 Web 會議記錄應該封存至 Exchange，不論 (或尚未將) 指派給使用者信箱的 In-Place 保留設定。</span><span class="sxs-lookup"><span data-stu-id="2d600-190">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="2d600-191">例如，若要設定使用者帳戶，使立即訊息和 Web 會議記錄永遠封存至 Exchange，您可以從商務用 Skype Server 管理命令介面中，使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="2d600-191">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Skype for Business Server Management Shell:</span></span>

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

<span data-ttu-id="2d600-192">若您想針對群組使用者 (例如，所有位於特定登錄器集區的使用者) 設定相同的封存原則，可使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="2d600-192">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

<span data-ttu-id="2d600-193">請注意，您必須使用商務用 Skype Server 管理命令介面 (和 Windows PowerShell) 才能設定 ExchangeArchivingPolicy 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="2d600-193">Note that you must use the Skype for Business Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="2d600-194">此屬性不會向商務用 Skype Server 中的系統管理員公開。</span><span class="sxs-lookup"><span data-stu-id="2d600-194">This property is not exposed to administrators in the Skype for Business Server.</span></span>

<span data-ttu-id="2d600-195">若您要檢視已指派特定封存原則之所有使用者的清單，您就可以使用類似下列的命令，即可傳回已將 ExchangeArchivingPolicy 屬性設為 Uninitialized 之所有使用者的 Active Directory 顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="2d600-195">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

<span data-ttu-id="2d600-196">同樣地，此命令會傳回已將 ExchangeArchivingPolicy 屬性設為 UseLyncArchivingPolicy 之使用者的顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="2d600-196">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```