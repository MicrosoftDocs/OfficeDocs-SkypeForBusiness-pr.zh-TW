---
title: 設定您的團隊目標階層
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 瞭解如何在組織中設定小組階層，將內容發佈給一大組團隊。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcdae04ce87db82bd5f18e818dcf194fc7ff38c7
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615039"
---
# <a name="set-up-your-team-targeting-hierarchy"></a><span data-ttu-id="c138e-103">設定您的團隊目標階層</span><span class="sxs-lookup"><span data-stu-id="c138e-103">Set up your team targeting hierarchy</span></span>

<span data-ttu-id="c138e-104">設定團隊目標階層可允許貴組織將內容發佈至一組大型團隊。</span><span class="sxs-lookup"><span data-stu-id="c138e-104">Setting up a team targeting hierarchy will allow your organization to publish content to a large set of teams.</span></span> <span data-ttu-id="c138e-105">團隊目標階層會定義您階層中所有團隊如何彼此關聯、哪些使用者可以發佈工作，以及哪些團隊使用者有權發佈工作。</span><span class="sxs-lookup"><span data-stu-id="c138e-105">The team targeting hierarchy defines how all the teams in your hierarchy are related to each other, which users can publish tasks, and which teams users have permissions to publish to.</span></span> <span data-ttu-id="c138e-106">除非為貴組織設定小組目標階層，否則所有使用者的發佈功能均會停用。</span><span class="sxs-lookup"><span data-stu-id="c138e-106">Publishing features are disabled for all users unless a team targeting hierarchy is set up for your organization.</span></span> <span data-ttu-id="c138e-107">若要設定團隊目標階層，您必須建立定義階層的檔案，然後將它上傳到 Teams 以將其套用至您的組織。</span><span class="sxs-lookup"><span data-stu-id="c138e-107">To set up a team targeting hierarchy, you'll need to create a file that defines the hierarchy and then upload it to Teams to apply it to your organization.</span></span> <span data-ttu-id="c138e-108">上傳架構之後，Teams 中的應用程式就可以使用它。</span><span class="sxs-lookup"><span data-stu-id="c138e-108">After the schema is uploaded, apps within Teams can use it.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c138e-109">對於初次發行，只有工作應用程式支援階層式團隊。</span><span class="sxs-lookup"><span data-stu-id="c138e-109">For the initial release, only the Tasks app supports hierarchical teams.</span></span>  <span data-ttu-id="c138e-110">將小組目標階層適用于您的組織，將可啟用工作 [應用程式中](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) 的工作發佈。</span><span class="sxs-lookup"><span data-stu-id="c138e-110">Applying a team targeting hierarchy to your organization will enable [task publishing](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) in the Tasks app.</span></span> <span data-ttu-id="c138e-111">您不會在 Microsoft Teams 的其他國家/地區看到團隊階層。</span><span class="sxs-lookup"><span data-stu-id="c138e-111">You won't see a hierarchy of teams in other areas of Microsoft Teams.</span></span>

<span data-ttu-id="c138e-112">以下是 Teams 中工作應用程式中階層的顯示範例。</span><span class="sxs-lookup"><span data-stu-id="c138e-112">Here's an example of how the hierarchy is represented in the Tasks app in Teams.</span></span> <span data-ttu-id="c138e-113">建立工作清單之後，發佈小組的成員就可以選取收件者小組，將 (發佈) 傳送給該工作清單。</span><span class="sxs-lookup"><span data-stu-id="c138e-113">After a task list is created, members of the publishing team can then select the recipient teams to send (publish) the task list to.</span></span> <span data-ttu-id="c138e-114">選取團隊時，發佈小組可以按照階層、屬性或兩者的組合進行篩選。</span><span class="sxs-lookup"><span data-stu-id="c138e-114">When selecting teams, the publishing team can filter by hierarchy, by attributes, or a combination of both.</span></span><br>

![ [工作發佈] 的螢幕擷取畫面](media/manage-tasks-app-publish.png)

## <a name="terminology"></a><span data-ttu-id="c138e-116">術語</span><span class="sxs-lookup"><span data-stu-id="c138e-116">Terminology</span></span>

<span data-ttu-id="c138e-117">當您流覽階層時，下列詞彙非常重要。</span><span class="sxs-lookup"><span data-stu-id="c138e-117">The following terms will be important as you navigate hierarchies.</span></span> <span data-ttu-id="c138e-118">Teams 將稱為 **節點**。</span><span class="sxs-lookup"><span data-stu-id="c138e-118">Teams will be referred to as **nodes**.</span></span>

* <span data-ttu-id="c138e-119">**根節點** 是階層中最上方的節點。</span><span class="sxs-lookup"><span data-stu-id="c138e-119">**Root nodes** are the topmost nodes in the hierarchy.</span></span> <span data-ttu-id="c138e-120">在範例中，Retail Communications 是根節點。</span><span class="sxs-lookup"><span data-stu-id="c138e-120">In the example, Retail Communications is a root node.</span></span>
* <span data-ttu-id="c138e-121">**父節點\*\*\*\*和子節點** 是代表兩個連接節點之間關係的詞彙。</span><span class="sxs-lookup"><span data-stu-id="c138e-121">**Parent nodes** and **child nodes** are terms that represent a relationship between two connected nodes.</span></span> <span data-ttu-id="c138e-122">在範例中，區域 01 是區域 1 的子節點。</span><span class="sxs-lookup"><span data-stu-id="c138e-122">In the example, District 01 is a child node of Area 1.</span></span>
* <span data-ttu-id="c138e-123">多層級的小孩稱為圳 **圳**。</span><span class="sxs-lookup"><span data-stu-id="c138e-123">Multiple levels of children are referred to as **descendants**.</span></span> <span data-ttu-id="c138e-124">地區 01、市面 01、市面 03、市面 07、區 02 和區 03 都是區域 1 的一個區。</span><span class="sxs-lookup"><span data-stu-id="c138e-124">District 01, Store 01, Store 03, Store 07, District 02, and District 03 are all descendants of Area 1.</span></span>
* <span data-ttu-id="c138e-125">沒有子節點的節點稱為節點 **節點**。</span><span class="sxs-lookup"><span data-stu-id="c138e-125">A node with no children is called a **leaf node**.</span></span> <span data-ttu-id="c138e-126">它們位於階層的底部。</span><span class="sxs-lookup"><span data-stu-id="c138e-126">They are at the bottom of a hierarchy.</span></span>
* <span data-ttu-id="c138e-127">**收** 件者團隊是已選取以接收要發佈的一組特定內容的團隊。</span><span class="sxs-lookup"><span data-stu-id="c138e-127">**Recipient teams** are teams that have been selected to receive a specific set of content to be published.</span></span> <span data-ttu-id="c138e-128">它們必須是節點節點。</span><span class="sxs-lookup"><span data-stu-id="c138e-128">They must be leaf nodes.</span></span>

## <a name="plan-your-hierarchy"></a><span data-ttu-id="c138e-129">規劃階層</span><span class="sxs-lookup"><span data-stu-id="c138e-129">Plan your hierarchy</span></span>

<span data-ttu-id="c138e-130">在建立定義階層的架構之前，您需要進行一些規劃，並決定要如何塑造您的組織。</span><span class="sxs-lookup"><span data-stu-id="c138e-130">Before you create the schema that defines your hierarchy, you need to do some planning and decide how you want to shape your organization.</span></span>  <span data-ttu-id="c138e-131">其中一個優先專案是決定哪些組織群組需要將工作發佈至其他群組。</span><span class="sxs-lookup"><span data-stu-id="c138e-131">One of the first priorities is deciding which organizational groups need to publish tasks to other groups.</span></span> <span data-ttu-id="c138e-132">階層中的每個節點都代表工作組或群組。</span><span class="sxs-lookup"><span data-stu-id="c138e-132">Each node in the hierarchy represents a working group or group of groups.</span></span>

### <a name="permissions-to-publish"></a><span data-ttu-id="c138e-133">發佈許可權</span><span class="sxs-lookup"><span data-stu-id="c138e-133">Permissions to publish</span></span>

<span data-ttu-id="c138e-134">發佈許可權取決於使用者是階層中任何團隊的成員，以及該團隊或團隊集合與階層中其他團隊的關係。</span><span class="sxs-lookup"><span data-stu-id="c138e-134">Permission to publish depends on whether a user is a member of any teams in the hierarchy plus the relationship of that team or set of teams to other teams in the hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="c138e-135">團隊的擁有者也會獲得發佈許可權。</span><span class="sxs-lookup"><span data-stu-id="c138e-135">The owner of a team is also granted publishing permissions.</span></span>

* <span data-ttu-id="c138e-136">如果使用者是至少一個團隊的成員，且該團隊的階層中至少有一個團隊有專案，該使用者就可以發佈至這些團隊，而不需要成為所有想要發佈物件的團隊成員。</span><span class="sxs-lookup"><span data-stu-id="c138e-136">If a user is a member of at least one team that has descendants in the hierarchy, that user can publish to those descendants without being a member of all teams they want to publish to.</span></span>
* <span data-ttu-id="c138e-137">如果使用者是階層中至少一個團隊的成員，但並非任何在階層中擁有通知的團隊成員，該使用者就可以查看及接收來自其組織的已發佈內容。</span><span class="sxs-lookup"><span data-stu-id="c138e-137">If a user is a member of a least one team in the hierarchy but isn't a member of any team with descendants in the hierarchy, that user can see and receive published content from their organization.</span></span>
* <span data-ttu-id="c138e-138">如果使用者不是階層中任何團隊的成員，該使用者將不會看到任何發佈相關功能。</span><span class="sxs-lookup"><span data-stu-id="c138e-138">If a user isn't a member of any team in the hierarchy, that user won't see any publishing-related functionality.</span></span>

### <a name="guidelines"></a><span data-ttu-id="c138e-139">指引</span><span class="sxs-lookup"><span data-stu-id="c138e-139">Guidelines</span></span>

* <span data-ttu-id="c138e-140">每個組織只能有一個階層檔案。</span><span class="sxs-lookup"><span data-stu-id="c138e-140">There can only be one hierarchy file applied per organization.</span></span> <span data-ttu-id="c138e-141">不過，您可以在一個 CSV 檔案中，將貴組織的不同部分視為節點的不同階層。</span><span class="sxs-lookup"><span data-stu-id="c138e-141">However, you can include different parts of your organization together as distinct hierarchies of nodes within one CSV file.</span></span> <span data-ttu-id="c138e-142">例如，Contoso Pharmaceuticals 有一個 Pharmaceuticaly 根節點和零售根節點。</span><span class="sxs-lookup"><span data-stu-id="c138e-142">For example, Contoso Pharmaceuticals has a Pharmacy root node and a Retail root node.</span></span> <span data-ttu-id="c138e-143">兩個根節點有多個樹系列，而且兩者之間沒有重迭。</span><span class="sxs-lookup"><span data-stu-id="c138e-143">Both root nodes have multiple rows of descendants and there's no overlap between them.</span></span>
* <span data-ttu-id="c138e-144">只有節點可以是出版物的收件者。</span><span class="sxs-lookup"><span data-stu-id="c138e-144">Only leaf nodes can be recipients of a publication.</span></span> <span data-ttu-id="c138e-145">階層中的其他節點有助於選取出版物的收件者。</span><span class="sxs-lookup"><span data-stu-id="c138e-145">Other nodes in the hierarchy are helpful for selecting recipients of a publication.</span></span>
* <span data-ttu-id="c138e-146">團隊只能在階層中顯示一次。</span><span class="sxs-lookup"><span data-stu-id="c138e-146">A team can only be represented one time in a hierarchy.</span></span>
* <span data-ttu-id="c138e-147">階層可以包含最多 15，000 個節點。</span><span class="sxs-lookup"><span data-stu-id="c138e-147">A hierarchy can contain up to 15,000 nodes.</span></span> <span data-ttu-id="c138e-148">我們計畫與客戶合作，提高較大型組織的這項限制。</span><span class="sxs-lookup"><span data-stu-id="c138e-148">We plan to work with customers to raise this limit for larger organizations.</span></span>

### <a name="example-hierarchy"></a><span data-ttu-id="c138e-149">範例階層</span><span class="sxs-lookup"><span data-stu-id="c138e-149">Example hierarchy</span></span>

<span data-ttu-id="c138e-150">例如，在下列階層中，回收、通訊和人力資源可以將工作發佈至階層中的每個底部節點 (小組) ，但西北區域只能將工作發佈至紐約市和波多美市團隊。</span><span class="sxs-lookup"><span data-stu-id="c138e-150">For example, in the following hierarchy, Recall, Communications, and HR can publish tasks to every bottom node (team) in the hierarchy, but Northeast Zone can only publish tasks to the New York Store and Boston Store teams.</span></span> <span data-ttu-id="c138e-151">範例階層可讓回收、通訊和人力資源群組發佈適用于整個公司的工作，例如福利資訊或來自 CEO 的郵件。</span><span class="sxs-lookup"><span data-stu-id="c138e-151">The example hierarchy allows the Recall, Communications, and HR groups to publish tasks that apply to the entire company, such as benefits information or messages from the CEO.</span></span> <span data-ttu-id="c138e-152">北區只能將人員排程、天氣資訊等工作發佈至紐約市和波多美市團隊。</span><span class="sxs-lookup"><span data-stu-id="c138e-152">Northeast Zone can publish tasks like personnel scheduling, weather information, and so on, only to the New York Store and Boston Store teams.</span></span>

![團隊階層範例](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a><span data-ttu-id="c138e-154">建立階層</span><span class="sxs-lookup"><span data-stu-id="c138e-154">Create your hierarchy</span></span>

> [!NOTE]
> <span data-ttu-id="c138e-155">本文其餘部分將探討在發佈工作給收件者小組時設定小組階層。</span><span class="sxs-lookup"><span data-stu-id="c138e-155">The remainder of this article discusses setting up a team hierarchy in the context of publishing tasks to recipient teams.</span></span> <span data-ttu-id="c138e-156">請參閱 [Teams](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) 中組織的管理工作應用程式，以概觀瞭解工作應用程式，當啟用時，工作發佈會出現。</span><span class="sxs-lookup"><span data-stu-id="c138e-156">Refer to [Manage the Tasks app for your organization in Teams](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) for an overview of the Tasks app, where task publishing appears when enabled.</span></span>

<span data-ttu-id="c138e-157">定義階層的架構是以 CSV 檔案中的逗號分隔 () 為基礎。</span><span class="sxs-lookup"><span data-stu-id="c138e-157">The schema that defines your hierarchy is based on a comma-separated values (CSV) file.</span></span> <span data-ttu-id="c138e-158">CSV 檔案中的每個列會對應到團隊階層中的一個節點。</span><span class="sxs-lookup"><span data-stu-id="c138e-158">Each row in the CSV file corresponds to one node within the hierarchy of teams.</span></span> <span data-ttu-id="c138e-159">每一列都包含為階層中節點命名的資訊、選擇性地將節點連結至小組，以及可用來篩選支援該節點之應用程式中團隊的屬性。</span><span class="sxs-lookup"><span data-stu-id="c138e-159">Each row contains information that names the node within the hierarchy, optionally links it to a team, and includes attributes that can be used to filter teams in apps that support it.</span></span>

<span data-ttu-id="c138e-160">您也可以 **定義類別，** 發佈小組可以使用這些類別來整理收件者小組的內容，以便他們更輕鬆地查看、排序及專注于相關內容。</span><span class="sxs-lookup"><span data-stu-id="c138e-160">You can also define **buckets**, which are categories that the publishing team can use to organize content sent to recipient teams to make it easier for them to view, sort, and focus on relevant content.</span></span>

### <a name="add-required-columns"></a><span data-ttu-id="c138e-161">新增必要的欄</span><span class="sxs-lookup"><span data-stu-id="c138e-161">Add required columns</span></span>

<span data-ttu-id="c138e-162">CSV 檔案必須包含下列三欄，順序如下，從第一欄開始。</span><span class="sxs-lookup"><span data-stu-id="c138e-162">The CSV file must contain the following three columns, in the following order, starting at the first column.</span></span> <span data-ttu-id="c138e-163">節點必須連結至小組，其接收工作。</span><span class="sxs-lookup"><span data-stu-id="c138e-163">A node must be linked to a team for it to receive tasks.</span></span>

| <span data-ttu-id="c138e-164">欄名稱</span><span class="sxs-lookup"><span data-stu-id="c138e-164">Column name</span></span>   | <span data-ttu-id="c138e-165">必要</span><span class="sxs-lookup"><span data-stu-id="c138e-165">Required</span></span> | <span data-ttu-id="c138e-166">說明</span><span class="sxs-lookup"><span data-stu-id="c138e-166">Description</span></span>   |
----------------|----------|---------------|
| <span data-ttu-id="c138e-167">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c138e-167">DisplayName</span></span>    | <span data-ttu-id="c138e-168">是</span><span class="sxs-lookup"><span data-stu-id="c138e-168">Yes</span></span>      | <span data-ttu-id="c138e-169">此欄位是節點的名稱。</span><span class="sxs-lookup"><span data-stu-id="c138e-169">This field is the name of the node.</span></span> <span data-ttu-id="c138e-170">名稱最多隻能包含 100 個字元，而且只包含 A-Z、a-z 和 0-9 字元。</span><span class="sxs-lookup"><span data-stu-id="c138e-170">The name can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9.</span></span> <span data-ttu-id="c138e-171">節點名稱必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c138e-171">Node names must be unique.</span></span> |
| <span data-ttu-id="c138e-172">ParentName</span><span class="sxs-lookup"><span data-stu-id="c138e-172">ParentName</span></span>    | <span data-ttu-id="c138e-173">是</span><span class="sxs-lookup"><span data-stu-id="c138e-173">Yes</span></span>       | <span data-ttu-id="c138e-174">這是父節點的名稱。</span><span class="sxs-lookup"><span data-stu-id="c138e-174">This is the name of the parent node.</span></span> <span data-ttu-id="c138e-175">您在此處指定的值必須與父節點 **的 DisplayName** 欄位中的值完全相符。</span><span class="sxs-lookup"><span data-stu-id="c138e-175">The value you specify here must match the value in the **DisplayName** field of the parent node exactly.</span></span> <span data-ttu-id="c138e-176">如果您想要新增多個父節點，請以分號分隔每個父節點 (;) 。</span><span class="sxs-lookup"><span data-stu-id="c138e-176">If you want to add more than one parent node, separate each parent node name with a semicolon (;).</span></span> <span data-ttu-id="c138e-177">您最多可以新增 25 個父節點，每個父節點名稱最多可包含 2500 個字元。</span><span class="sxs-lookup"><span data-stu-id="c138e-177">You can add up to 25 parent nodes, and each parent node name can be up to 2500 characters long.</span></span> <span data-ttu-id="c138e-178">只有當父節點是根節點時，節點才能有多個父節點。</span><span class="sxs-lookup"><span data-stu-id="c138e-178">A node can have multiple parent nodes only if the parent nodes are root nodes.</span></span>   <br><br><span data-ttu-id="c138e-179">**重要** 請小心不要建立迴圈，讓階層中較高的父項參照階層中較低階層中的子節點。</span><span class="sxs-lookup"><span data-stu-id="c138e-179">**IMPORTANT** Be careful not to create a loop where a parent higher up in the hierarchy references a child node lower in the hierarchy.</span></span> <span data-ttu-id="c138e-180">不支援這項功能。</span><span class="sxs-lookup"><span data-stu-id="c138e-180">This isn't supported.</span></span> |
| <span data-ttu-id="c138e-181">TeamId</span><span class="sxs-lookup"><span data-stu-id="c138e-181">TeamId</span></span>        | <span data-ttu-id="c138e-182">是，如果小組發佈工作或接收來自父節點的工作</span><span class="sxs-lookup"><span data-stu-id="c138e-182">Yes, if the team publishes tasks or receives tasks from a parent node</span></span>       | <span data-ttu-id="c138e-183">這包含您想要連結節點的團隊識別碼。</span><span class="sxs-lookup"><span data-stu-id="c138e-183">This contains the ID of the team you want to link a node to.</span></span> <span data-ttu-id="c138e-184">每個節點必須參照唯一的團隊，因此每個 TeamId 值可能只會出現在階層檔案中一次。</span><span class="sxs-lookup"><span data-stu-id="c138e-184">Each node must refer to a unique team, so each TeamId value may appear only once in the hierarchy file.</span></span> <span data-ttu-id="c138e-185">若要取得您想要連結節點的團隊識別碼，請執行下列 PowerShell 命令 `Get-Team | Export-Csv TeamList.csv` ：</span><span class="sxs-lookup"><span data-stu-id="c138e-185">To get the ID of a team you want to link a node to, run the following PowerShell command: `Get-Team | Export-Csv TeamList.csv`.</span></span> <span data-ttu-id="c138e-186">此命令會列出貴組織的團隊，並包含每個團隊的名稱和識別碼。</span><span class="sxs-lookup"><span data-stu-id="c138e-186">This command lists the teams in your organization and includes the name and ID for each team.</span></span> <span data-ttu-id="c138e-187">尋找您想要連結的團隊名稱，然後將識別碼複製到此欄位。</span><span class="sxs-lookup"><span data-stu-id="c138e-187">Find the name of the team you want to link to, and then copy the ID into this field.</span></span>|

> [!NOTE]
> <span data-ttu-id="c138e-188">如果節點不是根節點或節點，而且您不需要團隊成員資格來授予發佈和報表的對應許可權，您可以將 TeamId 保留空白。</span><span class="sxs-lookup"><span data-stu-id="c138e-188">If a node isn't a root node or a leaf node and you don't need the team membership to grant the corresponding permissions for publishing and reporting, you can leave the TeamId blank.</span></span> <span data-ttu-id="c138e-189">這個方法可用來在選擇收件者團隊時增加更細微度，或檢視完成報告而不擁有對應的小組。</span><span class="sxs-lookup"><span data-stu-id="c138e-189">This method can be used to add more granularity when choosing recipient teams or for viewing completion reports without having a corresponding team.</span></span>

### <a name="add-attribute-columns"></a><span data-ttu-id="c138e-190">新增屬性欄</span><span class="sxs-lookup"><span data-stu-id="c138e-190">Add attribute columns</span></span>

<span data-ttu-id="c138e-191">新增三個必要的欄之後，您可以新增選擇性的屬性欄。</span><span class="sxs-lookup"><span data-stu-id="c138e-191">After you add the three required columns, you can add optional attribute columns.</span></span> <span data-ttu-id="c138e-192">這些屬性可用來篩選節點，以便更輕鬆地選取要發佈工作的工作。</span><span class="sxs-lookup"><span data-stu-id="c138e-192">These attributes can be used to filter nodes so that you can more easily select the ones you want to publish tasks to.</span></span> <span data-ttu-id="c138e-193">根據該屬性的值互斥性，有兩種方法可以定義屬性。</span><span class="sxs-lookup"><span data-stu-id="c138e-193">There are two ways to define your attributes, depending on whether values for that attribute are mutually exclusive.</span></span>

|<span data-ttu-id="c138e-194">新增屬性的方法</span><span class="sxs-lookup"><span data-stu-id="c138e-194">Ways to add attributes</span></span>|<span data-ttu-id="c138e-195">說明</span><span class="sxs-lookup"><span data-stu-id="c138e-195">Description</span></span> |<span data-ttu-id="c138e-196">範例</span><span class="sxs-lookup"><span data-stu-id="c138e-196">Example</span></span>  |
|---|---------|---------|
|<span data-ttu-id="c138e-197">如果屬性的值互斥，則您指定的欄名稱會變成屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="c138e-197">If the values for an attribute are mutually exclusive, the column name you specify becomes the name of the attribute.</span></span>|<span data-ttu-id="c138e-198">每個資料列可以包含該屬性的一個值，而每個屬性欄可以有最多 50 個唯一值。</span><span class="sxs-lookup"><span data-stu-id="c138e-198">Each row can contain one value for that attribute, and each attribute column can have up to 50 unique values.</span></span> <span data-ttu-id="c138e-199">每個值最多隻能有 100 個字元。</span><span class="sxs-lookup"><span data-stu-id="c138e-199">Each value can be up to 100 characters long.</span></span> <span data-ttu-id="c138e-200">當您使用團隊目標階層選取收件者團隊時，在屬性欄中指定的一組屬性值會顯示為該屬性的篩選值。</span><span class="sxs-lookup"><span data-stu-id="c138e-200">The set of attribute values you specify in the attribute column will be displayed as filter values for that attribute when selecting recipient teams using the team targeting hierarchy.</span></span>|<span data-ttu-id="c138e-201">您希望使用者能夠根據版面配置篩選儲存區。</span><span class="sxs-lookup"><span data-stu-id="c138e-201">You want users to be able to filter stores by layout.</span></span> <span data-ttu-id="c138e-202">這個屬性的值互斥，因為商店只能有一個版面配置。</span><span class="sxs-lookup"><span data-stu-id="c138e-202">The values for this attribute are mutually exclusive because a store can have only one layout.</span></span> <br><br><span data-ttu-id="c138e-203">若要新增屬性以根據版面配置篩選儲存區，請新增名為 Store 版面配置的資料行。</span><span class="sxs-lookup"><span data-stu-id="c138e-203">To add an attribute to filter stores by layout, add a column named Store layout.</span></span> <span data-ttu-id="c138e-204">在此範例中，Store 版面配置屬性的值為壓縮、標準及大型。</span><span class="sxs-lookup"><span data-stu-id="c138e-204">In this example, values for the Store layout attribute are Compact, Standard, and Large.</span></span>
|<span data-ttu-id="c138e-205">如果您需要為屬性指定多個值，且這些值並非互斥，請使用 **屬性名稱：UniqueValue** 格式做為欄名。</span><span class="sxs-lookup"><span data-stu-id="c138e-205">If you need to indicate multiple values for an attribute and the values aren't mutually exclusive, use the **AttributeName:UniqueValue** format for the column names.</span></span> <br><br><span data-ttu-id="c138e-206">**重要** 請確定使用僅英文冒號 (：) unicode 做為屬性欄分隔符號。</span><span class="sxs-lookup"><span data-stu-id="c138e-206">**IMPORTANT** Make sure to use the English-only colon (:) as unicode isn't supported as an attribute column delimiter.</span></span> |<span data-ttu-id="c138e-207">冒號前的文字字串 (：) 成為屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="c138e-207">The text string before the colon (:) becomes the name of the attribute.</span></span> <span data-ttu-id="c138e-208">在冒號 (：) 之前包含相同文字字串的所有欄，會分組到篩選功能表中的區段。</span><span class="sxs-lookup"><span data-stu-id="c138e-208">All columns that contain the same text string before the colons (:) are grouped together into a section in the filtering menu.</span></span> <span data-ttu-id="c138e-209">冒號後的每一個字串都會變成該區段的值。</span><span class="sxs-lookup"><span data-stu-id="c138e-209">Each of the strings after the colon become the values for that section.</span></span><br><br><span data-ttu-id="c138e-210">每個資料列的值為 0 (為零) 該屬性為 1。</span><span class="sxs-lookup"><span data-stu-id="c138e-210">Each row can have a value of 0 (zero) or 1 for that attribute.</span></span> <span data-ttu-id="c138e-211">值為 0 表示屬性不適用於節點，而值 1 表示屬性會適用于該節點。</span><span class="sxs-lookup"><span data-stu-id="c138e-211">A value of 0 means that the attribute doesn't apply to the node and a value of 1 means that the attribute applies to that node.</span></span>|<span data-ttu-id="c138e-212">您希望使用者能夠根據部門篩選儲存區。</span><span class="sxs-lookup"><span data-stu-id="c138e-212">You want users to be able to filter stores by department.</span></span> <span data-ttu-id="c138e-213">商店可以有多個部門，因此這個屬性的值並非互斥。</span><span class="sxs-lookup"><span data-stu-id="c138e-213">A store can have multiple departments and so the values for this attribute aren't mutually exclusive.</span></span><br><br><span data-ttu-id="c138e-214">在此範例中，我們會新增部門：服裝、部門：電子、部門：食物、部門：家用及園藝、部門：運動用品做為屬性欄。</span><span class="sxs-lookup"><span data-stu-id="c138e-214">In this example, we add Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting goods as attribute columns.</span></span> <span data-ttu-id="c138e-215">部門會變成屬性名稱，使用者可以根據服裝、電子、食物、家用及園藝以及運動用品部門進行篩選。</span><span class="sxs-lookup"><span data-stu-id="c138e-215">Departments becomes the attribute name and users can filter by the Clothing, Electronics, Foods, Home and Garden, and Sporting goods departments.</span></span>|

<span data-ttu-id="c138e-216">當您新增屬性欄時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="c138e-216">When you add an attribute column, keep the following in mind:</span></span>

* <span data-ttu-id="c138e-217">您指定的欄名稱或您于冒號 (：) 之前指定的欄名稱，會成為屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="c138e-217">The column name you specify or the column name that you specify before the colon (:) becomes the name of the attribute.</span></span> <span data-ttu-id="c138e-218">此值會顯示在使用階層的 Teams 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="c138e-218">This value will be displayed in the Teams apps that use the hierarchy.</span></span>
* <span data-ttu-id="c138e-219">您階層中最多可以有 50 個屬性欄。</span><span class="sxs-lookup"><span data-stu-id="c138e-219">You can have up to 50 attribute columns in your hierarchy.</span></span>
* <span data-ttu-id="c138e-220">欄名最多隻能包含 100 個字元，而且只包含 A-Z、a-z 和 0-9 字元和空格。</span><span class="sxs-lookup"><span data-stu-id="c138e-220">The column name can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9, and spaces.</span></span> <span data-ttu-id="c138e-221">欄名稱必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c138e-221">Column names must be unique.</span></span>

### <a name="add-bucket-columns"></a><span data-ttu-id="c138e-222">新增資料桶欄</span><span class="sxs-lookup"><span data-stu-id="c138e-222">Add bucket columns</span></span>

<span data-ttu-id="c138e-223">您可以新增資料桶欄來建立可以組織工作之群組的容器。</span><span class="sxs-lookup"><span data-stu-id="c138e-223">You can add bucket columns to create buckets, which are groupings into which tasks can be organized.</span></span> <span data-ttu-id="c138e-224">每個容器在 CSV 檔案中都有自己的欄。</span><span class="sxs-lookup"><span data-stu-id="c138e-224">Each bucket gets its own column in the CSV file.</span></span> <span data-ttu-id="c138e-225">您建立的水鬥可供發佈小組使用。</span><span class="sxs-lookup"><span data-stu-id="c138e-225">The buckets you create are made available to the publishing team.</span></span> <span data-ttu-id="c138e-226">發佈小組就可以使用這些資料格來分類收件者小組的工作。</span><span class="sxs-lookup"><span data-stu-id="c138e-226">The publishing team can then use these buckets to categorize tasks for the recipient teams.</span></span> <span data-ttu-id="c138e-227">如果小組中還沒有一個資料桶，當工作發佈時，系統即會根據需求建立容器。</span><span class="sxs-lookup"><span data-stu-id="c138e-227">If a bucket doesn't already exist on a team, buckets are created on-demand when tasks are published.</span></span>

<span data-ttu-id="c138e-228">發佈小組可以集中將工作專案分類一次，為接收工作清單的所有十個、數百個或數千個收件者小組預先組織工作清單。</span><span class="sxs-lookup"><span data-stu-id="c138e-228">By categorizing the work items one time centrally, the publishing team can pre-organize the task list for all the tens, hundreds, or thousands of recipient teams that receive the task list.</span></span> <span data-ttu-id="c138e-229">然後，收件者小組可以排序及篩選工作，以專注于與工作最相關的區域。</span><span class="sxs-lookup"><span data-stu-id="c138e-229">The recipient teams can then sort and filter their tasks by bucket to focus on the area most relevant to their work.</span></span>

<span data-ttu-id="c138e-230">當您新增資料桶欄時，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="c138e-230">When you add a bucket column, note the following:</span></span>

* <span data-ttu-id="c138e-231">資料行名稱會變成資料桶的名稱。</span><span class="sxs-lookup"><span data-stu-id="c138e-231">The column name becomes the name of the bucket.</span></span> <span data-ttu-id="c138e-232">您指定的每個容器都會顯示在使用階層的 Teams 應用程式中的 Buckets 清單中。</span><span class="sxs-lookup"><span data-stu-id="c138e-232">Each bucket you specify will appear in the Buckets list in the Teams apps that use the hierarchy.</span></span>
* <span data-ttu-id="c138e-233">建議您不要在容器名稱中納入敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="c138e-233">We recommend that you don't include sensitive information in bucket names.</span></span> <span data-ttu-id="c138e-234">目前，發佈小組無法透過建立後透過發佈移除一個資料桶。</span><span class="sxs-lookup"><span data-stu-id="c138e-234">At this time, publishing teams can't remove a bucket through publishing after it's created.</span></span>
* <span data-ttu-id="c138e-235">欄名稱的前面必須帶有 # (#) 。</span><span class="sxs-lookup"><span data-stu-id="c138e-235">The column name must be preceded by a hashtag (#).</span></span> <span data-ttu-id="c138e-236">它最多隻能包含 100 個字元，而且只包含 A-Z、a-z 和 0-9 字元。</span><span class="sxs-lookup"><span data-stu-id="c138e-236">It can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9.</span></span> <span data-ttu-id="c138e-237">例如，#Operations和#Frozen貨物。</span><span class="sxs-lookup"><span data-stu-id="c138e-237">For example, #Operations and #Frozen Goods.</span></span>
* <span data-ttu-id="c138e-238">階層可以包含最多 25 個數據桶欄。</span><span class="sxs-lookup"><span data-stu-id="c138e-238">A hierarchy may contain up to 25 bucket columns.</span></span> <span data-ttu-id="c138e-239">我們計畫與客戶合作，提高較大型組織的此限制。</span><span class="sxs-lookup"><span data-stu-id="c138e-239">We plan to work with customers to increase this limit for larger organizations.</span></span>

### <a name="example"></a><span data-ttu-id="c138e-240">範例</span><span class="sxs-lookup"><span data-stu-id="c138e-240">Example</span></span>

<span data-ttu-id="c138e-241">以下是架構 CSV 檔案的範例，該檔案會建立以支援上一個影像中顯示的階層。</span><span class="sxs-lookup"><span data-stu-id="c138e-241">Here's an example of a schema CSV file that would be created to support the hierarchy shown in the previous image.</span></span> <span data-ttu-id="c138e-242">此架構包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="c138e-242">This schema contains the following:</span></span>

* <span data-ttu-id="c138e-243">三個名為 、 `TargetName` 和 `ParentName` 的必填欄 `TeamId`</span><span class="sxs-lookup"><span data-stu-id="c138e-243">Three required columns named `TargetName`, `ParentName`, and `TeamId`</span></span>
* <span data-ttu-id="c138e-244">三個名為 、 `Store layout` `Departments:Clothing``Departments:Foods`</span><span class="sxs-lookup"><span data-stu-id="c138e-244">Three attribute columns named `Store layout`, `Departments:Clothing`, and `Departments:Foods`</span></span>
* <span data-ttu-id="c138e-245">名稱為 、和的三個數據 `Fresh Foods` `Frozen Foods` 桶欄 `Women's Wear`</span><span class="sxs-lookup"><span data-stu-id="c138e-245">Three bucket columns named `Fresh Foods`, `Frozen Foods`, and `Women's Wear`</span></span>

<span data-ttu-id="c138e-246">屬性 `Store layout` 具有包含 、和 `Compact` `Standard` 的值 `Large` 。</span><span class="sxs-lookup"><span data-stu-id="c138e-246">The `Store layout` attribute has values that include `Compact`, `Standard`, and `Large`.</span></span> <span data-ttu-id="c138e-247">屬性 `Departments` 欄可以設定為 (或 `0`) 的值 `1` 。</span><span class="sxs-lookup"><span data-stu-id="c138e-247">The `Departments` attribute columns can be set to a value of `0` (zero) or `1`.</span></span> <span data-ttu-id="c138e-248">上述 `Store` 影像 `Departments` 不會顯示版面配置和屬性。</span><span class="sxs-lookup"><span data-stu-id="c138e-248">The `Store` layout and `Departments` attributes aren't shown in the image above.</span></span> <span data-ttu-id="c138e-249">它們新增在這裡，可協助顯示如何將屬性新增到節點專案。</span><span class="sxs-lookup"><span data-stu-id="c138e-249">They're added here to help show how attributes can be added to node entries.</span></span> <span data-ttu-id="c138e-250">這三個數據鬥欄也是一樣的。</span><span class="sxs-lookup"><span data-stu-id="c138e-250">The same is true for the three bucket columns.</span></span>

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,,,,,,,
East Regional Office,,,,,,,,
West Regional Office,,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a><span data-ttu-id="c138e-251">使用階層</span><span class="sxs-lookup"><span data-stu-id="c138e-251">Apply your hierarchy</span></span>

<span data-ttu-id="c138e-252">在架構 CSV 檔案中定義階層之後，就可以將階層上傳到 Teams 了。</span><span class="sxs-lookup"><span data-stu-id="c138e-252">After you've defined your hierarchy in the schema CSV file, you're ready to upload it to Teams.</span></span> <span data-ttu-id="c138e-253">若要這麼做，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="c138e-253">To do this, run the following command.</span></span> <span data-ttu-id="c138e-254">您必須是全域系統管理員或 Teams 服務系統管理員，才能執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="c138e-254">You must be a global admin or Teams service admin to do this step.</span></span>

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a><span data-ttu-id="c138e-255">更新您的階層</span><span class="sxs-lookup"><span data-stu-id="c138e-255">Update your hierarchy</span></span>

<span data-ttu-id="c138e-256">您可以使用與上述相同的 PowerShell 命令來上傳新的階層，以取代舊的階層。</span><span class="sxs-lookup"><span data-stu-id="c138e-256">You can upload a new hierarchy to replace the old one using the same PowerShell command as above.</span></span> <span data-ttu-id="c138e-257">每次上傳新的階層時，它會取代先前的階層。</span><span class="sxs-lookup"><span data-stu-id="c138e-257">Each time you upload a new hierarchy, it replaces the previous hierarchy.</span></span>

### <a name="check-the-status-of-your-hierarchy"></a><span data-ttu-id="c138e-258">檢查階層的狀態</span><span class="sxs-lookup"><span data-stu-id="c138e-258">Check the status of your hierarchy</span></span>

<span data-ttu-id="c138e-259">您可以執行下列命令來檢查階層上傳的狀態。</span><span class="sxs-lookup"><span data-stu-id="c138e-259">You can run the following command to check the status of your hierarchy upload.</span></span>

```powershell
Get-TeamTargetingHierarchyStatus
```

<span data-ttu-id="c138e-260">該命令會返回下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="c138e-260">The command will return the following fields:</span></span>

<span data-ttu-id="c138e-261">領域</span><span class="sxs-lookup"><span data-stu-id="c138e-261">Field</span></span>|<span data-ttu-id="c138e-262">說明</span><span class="sxs-lookup"><span data-stu-id="c138e-262">Description</span></span>
-----|------------
<span data-ttu-id="c138e-263">Id</span><span class="sxs-lookup"><span data-stu-id="c138e-263">Id</span></span> | <span data-ttu-id="c138e-264">上傳的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c138e-264">The unique ID for the upload.</span></span>
<span data-ttu-id="c138e-265">地位</span><span class="sxs-lookup"><span data-stu-id="c138e-265">Status</span></span> | <span data-ttu-id="c138e-266">上傳狀態。</span><span class="sxs-lookup"><span data-stu-id="c138e-266">Upload status.</span></span> <span data-ttu-id="c138e-267">值包括 **開始**、**驗證\*\*\*\*、成功** 和 **失敗**</span><span class="sxs-lookup"><span data-stu-id="c138e-267">Values include **Starting**, **Validating**, **Successful**, and **Failed**</span></span>
<span data-ttu-id="c138e-268">ErrorDetails</span><span class="sxs-lookup"><span data-stu-id="c138e-268">ErrorDetails</span></span> | <span data-ttu-id="c138e-269">是否有上傳錯誤的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c138e-269">Details if there's an upload error.</span></span> <span data-ttu-id="c138e-270">有關錯誤詳細資料的詳細資訊，請參閱疑難排解一節。</span><span class="sxs-lookup"><span data-stu-id="c138e-270">For more information about the error details, see the Troubleshooting section.</span></span> <span data-ttu-id="c138e-271">如果沒有錯誤，此欄位為空白。</span><span class="sxs-lookup"><span data-stu-id="c138e-271">If there's no error, this field is blank.</span></span>
<span data-ttu-id="c138e-272">LastUpdatedAt</span><span class="sxs-lookup"><span data-stu-id="c138e-272">LastUpdatedAt</span></span> | <span data-ttu-id="c138e-273">檔案上次更新的時間戳記和日期。</span><span class="sxs-lookup"><span data-stu-id="c138e-273">Timestamp and date of when the file was last updated.</span></span>
<span data-ttu-id="c138e-274">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="c138e-274">LastModifiedBy</span></span> | <span data-ttu-id="c138e-275">上次修改檔案之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="c138e-275">The ID of the last user who modified the file.</span></span>
<span data-ttu-id="c138e-276">檔案名</span><span class="sxs-lookup"><span data-stu-id="c138e-276">FileName</span></span> | <span data-ttu-id="c138e-277">CSV 的檔案名。</span><span class="sxs-lookup"><span data-stu-id="c138e-277">The file name of the CSV.</span></span>

## <a name="remove-your-hierarchy"></a><span data-ttu-id="c138e-278">移除階層</span><span class="sxs-lookup"><span data-stu-id="c138e-278">Remove your hierarchy</span></span>

<span data-ttu-id="c138e-279">如果您想要立即停用貴組織中所有使用者的已發佈清單選項卡，您可以移除您的階層。</span><span class="sxs-lookup"><span data-stu-id="c138e-279">If you want to immediately disable the **Published lists** tab for all users in your organization, you can remove your hierarchy.</span></span> <span data-ttu-id="c138e-280">使用者無法存取已發佈清單的選項卡或該選項卡上的任何功能。 這包括建立新工作清單以發佈、存取草稿清單、發佈、取消發佈和重複清單，以及查看報告的能力。</span><span class="sxs-lookup"><span data-stu-id="c138e-280">Users won't have access to the **Published lists** tab or any of the functionalities on the tab.  This includes the ability to create new task lists to publish, access draft lists, publish, unpublish, and duplicate lists, and view reporting.</span></span> <span data-ttu-id="c138e-281">移除階層不會解除發佈先前發佈的工作。</span><span class="sxs-lookup"><span data-stu-id="c138e-281">Removing the hierarchy doesn't unpublish tasks that were previously published.</span></span> <span data-ttu-id="c138e-282">這些工作仍然可供收件者小組完成。</span><span class="sxs-lookup"><span data-stu-id="c138e-282">These tasks will remain available for recipient teams to complete.</span></span>

<span data-ttu-id="c138e-283">若要移除您的階層，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="c138e-283">To remove your hierarchy, run the following command.</span></span> <span data-ttu-id="c138e-284">您必須是系統管理員才能執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="c138e-284">You must be an admin to perform this step.</span></span>

```powershell
Remove-TeamTargetingHierarchy
```

<span data-ttu-id="c138e-285">確認刪除時，狀態訊息仍然會顯示上一個架構存在，雖然嘗試再次刪除會出現錯誤，指出該物件為 Null。</span><span class="sxs-lookup"><span data-stu-id="c138e-285">When confirming deletion, the status message will still display the previous schema is present, although attempting to delete again returns an error that the object is null.</span></span>

## <a name="create-a-sample-hierarchy"></a><span data-ttu-id="c138e-286">建立範例階層</span><span class="sxs-lookup"><span data-stu-id="c138e-286">Create a sample hierarchy</span></span>

### <a name="install-the-teams-powershell-module"></a><span data-ttu-id="c138e-287">安裝 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="c138e-287">Install the Teams PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c138e-288">若要執行此步驟，您必須從 PowerShell 圖庫安裝並使用 Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公用預覽模組。</span><span class="sxs-lookup"><span data-stu-id="c138e-288">To perform this step, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="c138e-289">有關如何安裝模組的步驟，請參閱安裝[Teams PowerShell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="c138e-289">For steps on how to install the module, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

### <a name="sample-script"></a><span data-ttu-id="c138e-290">範例腳本</span><span class="sxs-lookup"><span data-stu-id="c138e-290">Sample script</span></span>

<span data-ttu-id="c138e-291">下列腳本可用來建立團隊，並上傳 .csv 檔案至您的 Microsoft Teams 租使用者。</span><span class="sxs-lookup"><span data-stu-id="c138e-291">The following script can be used to create the teams and upload a .csv file to your Microsoft Teams tenant.</span></span> <span data-ttu-id="c138e-292">如果您有現有的階層，此腳本將會取代它。</span><span class="sxs-lookup"><span data-stu-id="c138e-292">If you have an existing hierarchy, this script will replace it.</span></span>

#### <a name="create-teams-for-a-simple-hierarchy"></a><span data-ttu-id="c138e-293">為簡單的階層建立團隊</span><span class="sxs-lookup"><span data-stu-id="c138e-293">Create teams for a simple hierarchy</span></span>

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a><span data-ttu-id="c138e-294">使用小組資料在 DisplayName、ParentName、TeamId (中建立逗號分隔) </span><span class="sxs-lookup"><span data-stu-id="c138e-294">Use team data to create comma-separated output (DisplayName, ParentName, TeamId)</span></span>

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a><span data-ttu-id="c138e-295">將輸出儲存到下載資料夾中的 **.csv** 檔案</span><span class="sxs-lookup"><span data-stu-id="c138e-295">Save output to a .csv file in the **Downloads** folder</span></span>

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a><span data-ttu-id="c138e-296">上傳階層</span><span class="sxs-lookup"><span data-stu-id="c138e-296">Upload the hierarchy</span></span>

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a><span data-ttu-id="c138e-297">疑難排解</span><span class="sxs-lookup"><span data-stu-id="c138e-297">Troubleshooting</span></span>

### <a name="how-to-view-error-details"></a><span data-ttu-id="c138e-298">如何查看錯誤詳細資料</span><span class="sxs-lookup"><span data-stu-id="c138e-298">How to view error details</span></span>

<span data-ttu-id="c138e-299">您可以執行下列命令以瞭解造成錯誤的原因，並返回錯誤詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c138e-299">You can run the following command to understand what is causing an error and return the error details.</span></span>

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a><span data-ttu-id="c138e-300">上傳架構 CSV 檔案時，您會收到錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="c138e-300">You receive an error message when you upload your schema CSV file</span></span>

<span data-ttu-id="c138e-301">請注意錯誤訊息，因為錯誤訊息應包含疑難排解資訊，指出架構無法上傳的原因。</span><span class="sxs-lookup"><span data-stu-id="c138e-301">Take note of the error message as it should include troubleshooting information to indicate why the schema couldn't be uploaded.</span></span> <span data-ttu-id="c138e-302">根據錯誤訊息中的資訊，檢查並編輯架構 CSV 檔案，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="c138e-302">Review and edit your schema CSV file based on the information in the error message and then try again.</span></span>

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a><span data-ttu-id="c138e-303">上傳架構 CSV 檔案時，您會收到「錯誤：InvalidTeamId」錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="c138e-303">You receive an "Error: InvalidTeamId" error message when you upload your schema CSV file</span></span>

<span data-ttu-id="c138e-304">當您嘗試上傳架構 CSV 檔案時，您收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="c138e-304">When you try to upload your schema CSV file, you get the following error message:</span></span>

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

<span data-ttu-id="c138e-305">檢查確認您為架構 CSV 檔案中的小組使用正確的 TeamId。</span><span class="sxs-lookup"><span data-stu-id="c138e-305">Check to make sure that you're using the correct TeamId for the team in your schema CSV file.</span></span> <span data-ttu-id="c138e-306">TeamId 應該與支援小組的 Microsoft 365 群組群組識別碼相同。</span><span class="sxs-lookup"><span data-stu-id="c138e-306">The TeamId should be the same as the Group ID of the Microsoft 365 group that backs the team.</span></span> <span data-ttu-id="c138e-307">您可以在 Microsoft Teams 系統管理中心中查看團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="c138e-307">You can look up the Group ID of the team in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="c138e-308">在 [Microsoft Teams](https://admin.teams.microsoft.com/)系統管理中心的左側流覽中，前往 **Teams**  >  **管理團隊**。</span><span class="sxs-lookup"><span data-stu-id="c138e-308">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams** > **Manage teams**.</span></span>
2. <span data-ttu-id="c138e-309">如果 **表格未** 顯示群組識別碼欄，請選取表格右上角的編輯欄，然後開啟 **群組識別碼**。</span><span class="sxs-lookup"><span data-stu-id="c138e-309">If the **Group ID** column isn't displayed in the table, select **Edit columns** in the upper-right corner of the table, and then turn on **Group ID**.</span></span>
3. <span data-ttu-id="c138e-310">在清單中尋找團隊，然後找出群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="c138e-310">Find the team in the list, and then locate the Group ID.</span></span>

<span data-ttu-id="c138e-311">請確定架構 CSV 檔案中的 TeamId 與 Microsoft Teams 系統管理中心中顯示的群組識別碼一樣。</span><span class="sxs-lookup"><span data-stu-id="c138e-311">Make sure that the TeamId in your schema CSV file matches the Group ID that's displayed in the Microsoft Teams admin center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c138e-312">相關主題</span><span class="sxs-lookup"><span data-stu-id="c138e-312">Related topics</span></span>

* [<span data-ttu-id="c138e-313">在 Teams 中管理貴組織的工作應用程式</span><span class="sxs-lookup"><span data-stu-id="c138e-313">Manage the Tasks app for your organization in Teams</span></span>](manage-tasks-app.md)
* [<span data-ttu-id="c138e-314">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="c138e-314">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
