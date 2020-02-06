---
title: 將商務用 Skype 伺服器設定為使用 Exchange 伺服器封存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：設定 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server 的 IM 記錄。
ms.openlocfilehash: d8d97fc455521b2557064a683f7b19553a9642d3
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797004"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a><span data-ttu-id="d89f0-103">將商務用 Skype 伺服器設定為使用 Exchange 伺服器封存</span><span class="sxs-lookup"><span data-stu-id="d89f0-103">Configure Skype for Business Server to use Exchange Server archiving</span></span>

<span data-ttu-id="d89f0-104">**摘要：** 設定 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server 的 IM 記錄。</span><span class="sxs-lookup"><span data-stu-id="d89f0-104">**Summary:** Configure IM transcripts for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>

<span data-ttu-id="d89f0-105">商務用 Skype Server 可讓系統管理員選擇將即時消息和網路會議記錄歸檔至使用者的 Exchange Server 2016 或 Exchange Server 2013 信箱，而不是 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="d89f0-105">Skype for Business Server gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Exchange Server 2016 or Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="d89f0-106">如果您啟用此選項，則會在使用者的信箱中，將 [文字] 寫入 [清除] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d89f0-106">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="d89f0-107">[清除] 資料夾是一個隱藏資料夾，位於 [可復原的專案] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="d89f0-107">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="d89f0-108">雖然最終使用者看不到此資料夾，但資料夾是由 Exchange 搜尋引擎編制索引，而且可以使用 Exchange 信箱搜尋和/或 Microsoft SharePoint Server 2013 來探索。</span><span class="sxs-lookup"><span data-stu-id="d89f0-108">Although this folder is not visible to end users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="d89f0-109">由於資訊是儲存在 Exchange 就地保留功能所使用的同一個資料夾（負責封存電子郵件和其他 Exchange 通訊），因此系統管理員可以使用單一工具來搜尋所有存檔的電子通訊使用者名.</span><span class="sxs-lookup"><span data-stu-id="d89f0-109">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d89f0-110">若要完全停用交談封存，您也必須停用交談記錄。</span><span class="sxs-lookup"><span data-stu-id="d89f0-110">To completely disable conversation archiving, you must also disable conversation history.</span></span> <span data-ttu-id="d89f0-111">如需詳細資訊，請參閱下列主題：[管理商務用 Skype Server、CsClientPolicy 及 CsClientPolicy 中內部與外部通訊](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx)的封存。 [](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d89f0-111">For more information, see the following topics: [Managing the Archiving of internal and external communications in Skype for Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps), and [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span>

<span data-ttu-id="d89f0-112">若要將檔封存至 Exchange Server，您必須先在商務用 Skype Server 與 Exchange Server 之間設定伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="d89f0-112">In order to archive transcripts to Exchange Server you must begin by configuring server-to-server authentication between Skype for Business Server and Exchange Server.</span></span> <span data-ttu-id="d89f0-113">在進行伺服器對伺服器驗證之後，您可以在商務用 Skype Server 中執行下列工作（請注意，視您的設定和設定而定，您可能不需要完成這些工作）：</span><span class="sxs-lookup"><span data-stu-id="d89f0-113">After server-to-server authentication is in place, you can then carry out the following tasks in Skype for Business Server (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1. <span data-ttu-id="d89f0-114">修改您的商務用 Skype 伺服器封存設定設定，以啟用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-114">Enable Exchange archiving by modifying your Skype for Business Server archiving configuration settings.</span></span> <span data-ttu-id="d89f0-115">所有部署都必須執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="d89f0-115">This step is required for all deployments.</span></span>

2. <span data-ttu-id="d89f0-116">針對您的使用者啟用內部與/或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-116">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="d89f0-117">所有部署都必須執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="d89f0-117">This step is required for all deployments.</span></span>

3. <span data-ttu-id="d89f0-118">針對每位使用者設定 ExchangeArchivingPolicy 屬性。</span><span class="sxs-lookup"><span data-stu-id="d89f0-118">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="d89f0-119">只有在商務用 Skype 伺服器與 Exchange Server 位於不同的林中時，才需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="d89f0-119">This step is only required if Skype for Business Server and Exchange Server are located in different forests.</span></span>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="d89f0-120">步驟1：啟用 Exchange 封存</span><span class="sxs-lookup"><span data-stu-id="d89f0-120">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="d89f0-121">商務用 Skype Server 中的封存主要是使用 [存檔設定] 進行管理。</span><span class="sxs-lookup"><span data-stu-id="d89f0-121">Archiving in Skype for Business Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="d89f0-122">當您安裝商務用 Skype Server 時，系統會自動提供這些設定的單一全域集合。</span><span class="sxs-lookup"><span data-stu-id="d89f0-122">When you install Skype for Business Server you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="d89f0-123">（系統管理員可以選擇在網站範圍中建立新的存檔設定集合）。根據預設，全域設定中不會啟用封存，也不會在這些設定中啟用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-123">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="d89f0-124">為了使用 Exchange 封存，系統管理員必須在這些設定設定中設定 EnableArchiving 和 EnableExchangeArchiving 屬性。</span><span class="sxs-lookup"><span data-stu-id="d89f0-124">In order to use Exchange archiving, administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="d89f0-125">EnableArchiving 屬性可以設定為三個可能值的其中之一：</span><span class="sxs-lookup"><span data-stu-id="d89f0-125">The EnableArchiving property can be set to one of three possible values:</span></span>

- <span data-ttu-id="d89f0-126">[**無**]。</span><span class="sxs-lookup"><span data-stu-id="d89f0-126">**None**.</span></span> <span data-ttu-id="d89f0-127">封存已停用。</span><span class="sxs-lookup"><span data-stu-id="d89f0-127">Archiving is disabled.</span></span> <span data-ttu-id="d89f0-128">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="d89f0-128">This is the default value.</span></span> <span data-ttu-id="d89f0-129">如果 EnableArchiving 設定為 [無]，則不會將任何內容封存在您的商務用 Skype Server 封存資料庫或 Exchange Server 中。</span><span class="sxs-lookup"><span data-stu-id="d89f0-129">If EnableArchiving is set to None then nothing will be archived in either your Skype for Business Server archiving database or in Exchange Server.</span></span>

- <span data-ttu-id="d89f0-130">**ImOnly**。</span><span class="sxs-lookup"><span data-stu-id="d89f0-130">**ImOnly**.</span></span> <span data-ttu-id="d89f0-131">只封存立即訊息記錄。</span><span class="sxs-lookup"><span data-stu-id="d89f0-131">Only instant message transcripts are archived.</span></span> <span data-ttu-id="d89f0-132">如果啟用 Exchange 封存，這些記錄將會在 Exchange Server 中封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-132">If Exchange archiving is enabled, these transcripts will be archived in Exchange Server.</span></span> <span data-ttu-id="d89f0-133">如果 Exchange 封存已停用，這些記錄將會封存到商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="d89f0-133">If Exchange archiving is disabled then these transcripts will be archived to Skype for Business Server.</span></span>

- <span data-ttu-id="d89f0-134">**ImAndWebConf**。</span><span class="sxs-lookup"><span data-stu-id="d89f0-134">**ImAndWebConf**.</span></span> <span data-ttu-id="d89f0-135">立即訊息記錄和網路會議記錄都已歸檔。</span><span class="sxs-lookup"><span data-stu-id="d89f0-135">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="d89f0-136">如果啟用 Exchange 封存，這些記錄將會在 Exchange Server 中封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-136">If Exchange archiving is enabled these transcripts will be archived in Exchange Server.</span></span> <span data-ttu-id="d89f0-137">如果 Exchange 封存已停用，這些記錄將會封存到商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="d89f0-137">If Exchange archiving is disabled then these transcripts will be archived to Skype for Business Server.</span></span>

<span data-ttu-id="d89f0-138">EnableExchangeArchiving 屬性是布林值：將 EnableExchangeArchiving 設定為 True （$True）以啟用 Exchange 封存，或將 EnableExchangeArchiving 設定為 False （$False）來停用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-138">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="d89f0-139">例如，這個命令可讓您封存立即訊息記錄，同時也能啟用 Exchange 封存：</span><span class="sxs-lookup"><span data-stu-id="d89f0-139">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

<span data-ttu-id="d89f0-140">若要停用 Exchange 封存，請使用類似下列的命令來啟用立即訊息歸檔，但會停用 Exchange （換句話說，記錄會歸檔到商務用 Skype Server）：</span><span class="sxs-lookup"><span data-stu-id="d89f0-140">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Skype for Business Server):</span></span>

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> <span data-ttu-id="d89f0-141">如果 EnableArchiving 屬性設為 [無]，則商務用 Skype Server 將不會完全封存立即訊息和網路會議記錄。</span><span class="sxs-lookup"><span data-stu-id="d89f0-141">If the EnableArchiving property is set to None, then Skype for Business Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="d89f0-142">在這種情況下，伺服器會直接忽略針對 EnableExchangeArchiving 設定的值。</span><span class="sxs-lookup"><span data-stu-id="d89f0-142">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>

<span data-ttu-id="d89f0-143">您也可以使用商務用 Skype 伺服器來啟用（或停用） Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-143">Exchange archiving can also be enabled (or disabled) by using the Skype for Business Server.</span></span> <span data-ttu-id="d89f0-144">若要這樣做，請完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="d89f0-144">To do that, complete the following procedure:</span></span>

1. <span data-ttu-id="d89f0-145">在 [控制台] 中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="d89f0-145">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2. <span data-ttu-id="d89f0-146">在 [封存**配置**] 索引標籤上，按兩下要修改的封存設定集合（例如，**全域**集合）。</span><span class="sxs-lookup"><span data-stu-id="d89f0-146">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3. <span data-ttu-id="d89f0-147">在 [**編輯封存設定**] 窗格中，按一下 [封存**設定**] 下拉式清單，然後選取 [封存**im 會話**] （[只封存立即訊息會話]），或是 [封存**im 和網路**會議] 會話（以封存立即訊息和網路會議會話）。</span><span class="sxs-lookup"><span data-stu-id="d89f0-147">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4. <span data-ttu-id="d89f0-148">選擇要封存的專案之後，請選取 [ **Exchange Server 整合**] 核取方塊以啟用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-148">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="d89f0-149">若要停用 Exchange 封存，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d89f0-149">To disable Exchange archiving, clear this checkbox.</span></span>

> [!NOTE]
> <span data-ttu-id="d89f0-150">如果將 [封存]**設定**設為 [**停**用封存]，就無法使用 [ **Exchange Server 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d89f0-150">The **Exchange Server integration** checkbox will not be available if the **Archiving setting** is set to **Disable archiving**.</span></span> <span data-ttu-id="d89f0-151">您必須先啟用存檔，然後啟用 Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-151">You must enable archiving first and then enable Exchange archiving.</span></span>

<span data-ttu-id="d89f0-152">如果商務用 Skype Server 和 Exchange 伺服器位於同一個林中，則為個別使用者封存（或至少對於在 Exchange Server 上擁有電子郵件帳戶的使用者），則會使用 Exchange 就地保留原則來管理。</span><span class="sxs-lookup"><span data-stu-id="d89f0-152">If Skype for Business Server and Exchange Server are located in the same forest, then archiving for individual users (or at least for users who have email accounts on Exchange Server) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="d89f0-153">如果您的使用者是以舊版 Exchange 為宿主，則會使用商務用 Skype Server 封存原則來管理這些使用者的存檔。</span><span class="sxs-lookup"><span data-stu-id="d89f0-153">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Skype for Business Server archiving policies.</span></span> <span data-ttu-id="d89f0-154">請注意，只有 Exchange Server 2016 或 Exchange Server 2013 帳戶的使用者才能將其商務用 Skype 記錄存檔至 Exchange。</span><span class="sxs-lookup"><span data-stu-id="d89f0-154">Note that only users with accounts on Exchange Server 2016 or Exchange Server 2013 can have their Skype for Business transcripts archived to Exchange.</span></span>

<span data-ttu-id="d89f0-155">如果商務用 Skype Server 和 Exchange Server 位於不同的林中，則會透過設定每個個別使用者帳戶的 ExchangeArchivingPolicy 屬性來管理針對個別使用者進行的存檔。</span><span class="sxs-lookup"><span data-stu-id="d89f0-155">If Skype for Business Server and Exchange Server are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="d89f0-156">如需詳細資訊，請參閱步驟3。</span><span class="sxs-lookup"><span data-stu-id="d89f0-156">See Step 3 for more information.</span></span>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="d89f0-157">步驟2：啟用內部及/或外部通訊的存檔</span><span class="sxs-lookup"><span data-stu-id="d89f0-157">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="d89f0-158">在您啟用封存功能之後（以及 Exchange 封存）之後，您必須修改適當的存檔原則，以確保使用者會話已實際封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-158">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="d89f0-159">請注意，只要啟用封存（步驟1），就不會讓商務用 Skype Server 開始封存立即訊息和網路會議記錄。</span><span class="sxs-lookup"><span data-stu-id="d89f0-159">Note that simply enabling archiving (Step 1) does not cause Skype for Business Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="d89f0-160">相反地，您必須使用封存原則來啟用內部及/或外部封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-160">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="d89f0-161">當您安裝商務用 Skype Server 時，您也會安裝單一、全域存檔策略，其中包含兩個屬性：</span><span class="sxs-lookup"><span data-stu-id="d89f0-161">When you install Skype for Business Server you also install a single, global archiving policy that contains two properties:</span></span>

- <span data-ttu-id="d89f0-162">**ArchiveInternal**。</span><span class="sxs-lookup"><span data-stu-id="d89f0-162">**ArchiveInternal**.</span></span> <span data-ttu-id="d89f0-163">當設定為 True （$True）時，表示只會封存涉及在貴組織中擁有 Active Directory 帳戶之使用者的內部通訊會話。</span><span class="sxs-lookup"><span data-stu-id="d89f0-163">When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

- <span data-ttu-id="d89f0-164">**ArchiveExternal**。</span><span class="sxs-lookup"><span data-stu-id="d89f0-164">**ArchiveExternal**.</span></span> <span data-ttu-id="d89f0-165">當設定為 True （$True）時，表示內部通訊會話（至少有一個使用者在貴組織中沒有 Active Directory 帳戶的會話）將會封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-165">When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="d89f0-166">根據預設，這些屬性值會設定為 False，表示不會封存內部或外部通訊會話。</span><span class="sxs-lookup"><span data-stu-id="d89f0-166">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="d89f0-167">若要修改全域原則，您可以使用商務用 Skype Server 管理命令介面和 CsArchivingPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d89f0-167">To modify the global policy, you can use the Skype for Business Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="d89f0-168">這個命令可讓您同時存檔內部和外部通訊會話：</span><span class="sxs-lookup"><span data-stu-id="d89f0-168">This command enables the archiving of both internal and external communication sessions:</span></span>

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

<span data-ttu-id="d89f0-169">或者，您也可以使用新的 CsArchivingPolicy，在網站範圍或每個使用者的範圍內建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="d89f0-169">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope.</span></span> <span data-ttu-id="d89f0-170">例如，這個命令會建立一個名為 RedmondArchivingPolicy 的新的每使用者存檔策略：</span><span class="sxs-lookup"><span data-stu-id="d89f0-170">For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

<span data-ttu-id="d89f0-171">如果您建立每個使用者的原則，您必須將該原則指派給適當的使用者。</span><span class="sxs-lookup"><span data-stu-id="d89f0-171">If you create a per-user policy you will then need to assign that policy to the appropriate users.</span></span> <span data-ttu-id="d89f0-172">例如：</span><span class="sxs-lookup"><span data-stu-id="d89f0-172">For example:</span></span>

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

<span data-ttu-id="d89f0-173">您也可以使用商務用 Skype Server 的 [控制台] 來管理歸檔原則。</span><span class="sxs-lookup"><span data-stu-id="d89f0-173">Archiving policies can also be managed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="d89f0-174">在 [控制台] 中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。</span><span class="sxs-lookup"><span data-stu-id="d89f0-174">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="d89f0-175">若要修改現有的原則，請按兩下原則（例如全域），然後在 [**編輯封存原則**] 窗格中，選取或清除 [封存**內部通訊**] 和 [封存**外部通訊**] 核取方塊（視需要）。</span><span class="sxs-lookup"><span data-stu-id="d89f0-175">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="d89f0-176">若要建立新的存檔原則，請按一下 [**新增**]，然後選取 [**網站原則**] 或 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="d89f0-176">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="d89f0-177">如果您建立新的使用者策略，您必須存取適當的使用者帳戶（從 [**使用者**] 索引標籤），並將這些使用者指派給新的原則。</span><span class="sxs-lookup"><span data-stu-id="d89f0-177">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="d89f0-178">步驟3：設定 ExchangeArchivingPolicy 屬性</span><span class="sxs-lookup"><span data-stu-id="d89f0-178">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="d89f0-179">如果商務用 Skype Server 和 Exchange Server 位於不同的林中，則在 [封存設定] 設定中只啟用 Exchange 封存是不夠的。這不會導致立即訊息和網路會議記錄在 Exchange 中進行封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-179">If Skype for Business Server and Exchange Server are located in different forests, then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="d89f0-180">相反地，您也必須在每一個相關的商務用 Skype Server 使用者帳戶上設定 ExchangeArchivingPolicy 屬性。</span><span class="sxs-lookup"><span data-stu-id="d89f0-180">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Skype for Business Server user accounts.</span></span> <span data-ttu-id="d89f0-181">這個屬性可以設定為四個可能值的其中之一：</span><span class="sxs-lookup"><span data-stu-id="d89f0-181">This property can be set to one of four possible values:</span></span>

1. <span data-ttu-id="d89f0-182">**未初始化**。</span><span class="sxs-lookup"><span data-stu-id="d89f0-182">**Uninitialized**.</span></span> <span data-ttu-id="d89f0-183">指出將根據針對使用者的 Exchange 信箱設定的就地保留設定來存檔;如果未在使用者的信箱上啟用就地保留，使用者將會在商務用 Skype Server 中將其訊息和網路會議記錄存檔。</span><span class="sxs-lookup"><span data-stu-id="d89f0-183">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Skype for Business Server.</span></span>

2. <span data-ttu-id="d89f0-184">**UseLyncArchivingPolicy**。</span><span class="sxs-lookup"><span data-stu-id="d89f0-184">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="d89f0-185">表示使用者的立即訊息和網路會議記錄應該在商務用 Skype 伺服器（而非 Exchange）中歸檔。</span><span class="sxs-lookup"><span data-stu-id="d89f0-185">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Skype for Business Server rather than in Exchange.</span></span>

3. <span data-ttu-id="d89f0-186">**NoArchiving**。</span><span class="sxs-lookup"><span data-stu-id="d89f0-186">**NoArchiving**.</span></span> <span data-ttu-id="d89f0-187">表示使用者的立即訊息和網路會議記錄根本不應進行封存。</span><span class="sxs-lookup"><span data-stu-id="d89f0-187">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="d89f0-188">請注意，此設定會覆寫指派給使用者的任何商務用 Skype Server 封存原則。</span><span class="sxs-lookup"><span data-stu-id="d89f0-188">Note that this setting overrides any Skype for Business Server archiving policies assigned to the user.</span></span>

4. <span data-ttu-id="d89f0-189">**ArchivingToExchange**。</span><span class="sxs-lookup"><span data-stu-id="d89f0-189">**ArchivingToExchange**.</span></span> <span data-ttu-id="d89f0-190">表示無論是否已將（或尚未）指派給使用者信箱的就地保留設定，都應該將使用者的立即訊息和網路會議記錄歸檔至 Exchange。</span><span class="sxs-lookup"><span data-stu-id="d89f0-190">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="d89f0-191">例如，若要設定使用者帳戶，讓立即訊息和網路會議記錄都能歸檔到 Exchange，您可以使用與商務用 Skype Server Management Shell 類似的命令：</span><span class="sxs-lookup"><span data-stu-id="d89f0-191">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Skype for Business Server Management Shell:</span></span>

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

<span data-ttu-id="d89f0-192">如果您想要為一組使用者設定相同的歸檔原則（例如，所有使用者都駐留在指定的註冊機構池中），您可以使用類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="d89f0-192">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

<span data-ttu-id="d89f0-193">請注意，您必須使用商務用 Skype Server Management Shell （與 Windows PowerShell），才能設定 ExchangeArchivingPolicy 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="d89f0-193">Note that you must use the Skype for Business Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="d89f0-194">這個屬性不會對商務用 Skype 伺服器的系統管理員公開。</span><span class="sxs-lookup"><span data-stu-id="d89f0-194">This property is not exposed to administrators in the Skype for Business Server.</span></span>

<span data-ttu-id="d89f0-195">如果您想要查看已獲指派特定歸檔原則之所有使用者的清單，您可以使用類似下列的命令，這會傳回已設定 ExchangeArchivingPolicy 屬性的所有使用者的 Active Directory 顯示名稱。取消初始化：</span><span class="sxs-lookup"><span data-stu-id="d89f0-195">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

<span data-ttu-id="d89f0-196">同樣地，這個命令會傳回沒有 ExchangeArchivingPolicy 屬性設定為 UseLyncArchivingPolicy 的使用者的顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="d89f0-196">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


