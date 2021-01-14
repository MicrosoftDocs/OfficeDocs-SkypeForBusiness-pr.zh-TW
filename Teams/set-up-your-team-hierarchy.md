---
title: 設定您的團隊目標階層
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 瞭解如何在組織中設定小組階層，以將內容發佈至大型小組。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06244553c051677533d275ad6cd47052775d01f7
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865247"
---
# <a name="set-up-your-team-targeting-hierarchy"></a><span data-ttu-id="38ea2-103">設定您的團隊目標階層</span><span class="sxs-lookup"><span data-stu-id="38ea2-103">Set up your team targeting hierarchy</span></span>

<span data-ttu-id="38ea2-104">設定團隊目標階層可讓您的組織將內容發佈至大型小組。</span><span class="sxs-lookup"><span data-stu-id="38ea2-104">Setting up a team targeting hierarchy will allow your organization to publish content to a large set of teams.</span></span> <span data-ttu-id="38ea2-105">團隊目標階層定義層次結構中的所有團隊如何彼此關聯，哪些使用者可以發佈工作，以及使用者有權發佈至哪些團隊。</span><span class="sxs-lookup"><span data-stu-id="38ea2-105">The team targeting hierarchy defines how all the teams in your hierarchy are related to each other, which users can publish tasks, and which teams users have permissions to publish to.</span></span> <span data-ttu-id="38ea2-106">除非針對您的組織設定團隊目標階層，否則所有使用者都停用發佈功能。</span><span class="sxs-lookup"><span data-stu-id="38ea2-106">Publishing features are disabled for all users unless a team targeting hierarchy is set up for your organization.</span></span> <span data-ttu-id="38ea2-107">若要設定團隊目標階層，您需要建立一個定義階層的檔案，然後將其上傳至團隊，將其套用到您的組織。</span><span class="sxs-lookup"><span data-stu-id="38ea2-107">To set up a team targeting hierarchy, you'll need to create a file that defines the hierarchy and then upload it to Teams to apply it to your organization.</span></span> <span data-ttu-id="38ea2-108">上傳架構之後，小組中的 app 就可以使用它。</span><span class="sxs-lookup"><span data-stu-id="38ea2-108">After the schema is uploaded, apps within Teams can use it.</span></span> <span data-ttu-id="38ea2-109">您可以在 [此處](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#Create-a-sample-hierarchy)練習使用腳本來設定階層並將其上傳到您的小組租使用者。</span><span class="sxs-lookup"><span data-stu-id="38ea2-109">You can practice setting up a hierarchy and uploading it to your Teams tenant using a script [here](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#Create-a-sample-hierarchy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38ea2-110">初次發行時，只有 [任務] app 支援階層式團隊。</span><span class="sxs-lookup"><span data-stu-id="38ea2-110">For the initial release, only the Tasks app supports hierarchical teams.</span></span>  <span data-ttu-id="38ea2-111">將團隊目標階層套用至您的組織將會在 [工作] app 中啟用 [任務發佈](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) 。</span><span class="sxs-lookup"><span data-stu-id="38ea2-111">Applying a team targeting hierarchy to your organization will enable [task publishing](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) in the Tasks app.</span></span> <span data-ttu-id="38ea2-112">在 Microsoft 團隊的其他區域中，您不會看到小組的階層。</span><span class="sxs-lookup"><span data-stu-id="38ea2-112">You won't see a hierarchy of teams in other areas of Microsoft Teams.</span></span>

<span data-ttu-id="38ea2-113">以下是在 [團隊] 中的 [工作] 應用程式中代表階層的範例。</span><span class="sxs-lookup"><span data-stu-id="38ea2-113">Here's an example of how the hierarchy is represented in the Tasks app in Teams.</span></span> <span data-ttu-id="38ea2-114">在工作清單建立之後，發佈小組的成員就可以選取要傳送的收件者小組 (發佈) 工作清單。</span><span class="sxs-lookup"><span data-stu-id="38ea2-114">After a task list is created, members of the publishing team can then select the recipient teams to send (publish) the task list to.</span></span> <span data-ttu-id="38ea2-115">選取小組時，發佈小組可以依階層、依屬性篩選，或是兩者的結合。</span><span class="sxs-lookup"><span data-stu-id="38ea2-115">When selecting teams, the publishing team can filter by hierarchy, by attributes, or a combination of both.</span></span><br>

![[任務發佈] 的螢幕擷取畫面](media/manage-tasks-app-publish.png)

## <a name="terminology"></a><span data-ttu-id="38ea2-117">詞彙</span><span class="sxs-lookup"><span data-stu-id="38ea2-117">Terminology</span></span>

<span data-ttu-id="38ea2-118">當您流覽階層時，下列字詞就很重要。</span><span class="sxs-lookup"><span data-stu-id="38ea2-118">The following terms will be important as you navigate hierarchies.</span></span> <span data-ttu-id="38ea2-119">團隊將稱為 **節點**。</span><span class="sxs-lookup"><span data-stu-id="38ea2-119">Teams will be referred to as **nodes**.</span></span>

* <span data-ttu-id="38ea2-120">**根節點** 是階層中最上層的節點。</span><span class="sxs-lookup"><span data-stu-id="38ea2-120">**Root nodes** are the topmost nodes in the hierarchy.</span></span> <span data-ttu-id="38ea2-121">在這個範例中，零售通訊是根節點。</span><span class="sxs-lookup"><span data-stu-id="38ea2-121">In the example, Retail Communications is a root node.</span></span>
* <span data-ttu-id="38ea2-122">**父節點** 和 **子節點** 是代表兩個連線節點之間關聯的字詞。</span><span class="sxs-lookup"><span data-stu-id="38ea2-122">**Parent nodes** and **child nodes** are terms that represent a relationship between two connected nodes.</span></span> <span data-ttu-id="38ea2-123">在這個範例中，地區01是區域1的子節點。</span><span class="sxs-lookup"><span data-stu-id="38ea2-123">In the example, District 01 is a child node of Area 1.</span></span>
* <span data-ttu-id="38ea2-124">多個子層級稱為 **後代**。</span><span class="sxs-lookup"><span data-stu-id="38ea2-124">Multiple levels of children are referred to as **descendants**.</span></span> <span data-ttu-id="38ea2-125">地區01，商店01，商店03，商店07，地區02，地區03則是區域1的所有後代。</span><span class="sxs-lookup"><span data-stu-id="38ea2-125">District 01, Store 01, Store 03, Store 07, District 02, and District 03 are all descendants of Area 1.</span></span>
* <span data-ttu-id="38ea2-126">沒有子節點的節點稱為 **葉節點**。</span><span class="sxs-lookup"><span data-stu-id="38ea2-126">A node with no children is called a **leaf node**.</span></span> <span data-ttu-id="38ea2-127">它們位於階層的底部。</span><span class="sxs-lookup"><span data-stu-id="38ea2-127">They are at the bottom of a hierarchy.</span></span>
* <span data-ttu-id="38ea2-128">[**收件者小組**] 是已選取要接收發布的一組特定內容的小組。</span><span class="sxs-lookup"><span data-stu-id="38ea2-128">**Recipient teams** are teams that have been selected to receive a specific set of content to be published.</span></span> <span data-ttu-id="38ea2-129">它們必須是葉節點。</span><span class="sxs-lookup"><span data-stu-id="38ea2-129">They must be leaf nodes.</span></span>

## <a name="plan-your-hierarchy"></a><span data-ttu-id="38ea2-130">規劃階層</span><span class="sxs-lookup"><span data-stu-id="38ea2-130">Plan your hierarchy</span></span>

<span data-ttu-id="38ea2-131">在建立定義階層的架構之前，必須先進行一些規劃，並決定您要如何為組織製作圖形。</span><span class="sxs-lookup"><span data-stu-id="38ea2-131">Before you create the schema that defines your hierarchy, you need to do some planning and decide how you want to shape your organization.</span></span>  <span data-ttu-id="38ea2-132">首先的其中一個優先順序是決定哪些組織群組需要將工作發佈至其他群組。</span><span class="sxs-lookup"><span data-stu-id="38ea2-132">One of the first priorities is deciding which organizational groups need to publish tasks to other groups.</span></span> <span data-ttu-id="38ea2-133">階層中的每個節點代表一個工作群組或群組群組。</span><span class="sxs-lookup"><span data-stu-id="38ea2-133">Each node in the hierarchy represents a working group or group of groups.</span></span>

### <a name="permissions-to-publish"></a><span data-ttu-id="38ea2-134">發佈許可權</span><span class="sxs-lookup"><span data-stu-id="38ea2-134">Permissions to publish</span></span>

<span data-ttu-id="38ea2-135">發佈的許可權取決於使用者是否為階層中任何團隊的成員，以及該團隊或團隊的關聯，以及階層中的其他團隊。</span><span class="sxs-lookup"><span data-stu-id="38ea2-135">Permission to publish depends on whether a user is a member of any teams in the hierarchy plus the relationship of that team or set of teams to other teams in the hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="38ea2-136">小組擁有者也被授與發佈許可權。</span><span class="sxs-lookup"><span data-stu-id="38ea2-136">The owner of a team is also granted publishing permissions.</span></span>

* <span data-ttu-id="38ea2-137">如果使用者是至少一個團隊的成員，且階層中有後代，該使用者就可以發佈到這些後代，而不是他們想要發佈至所有團隊的成員。</span><span class="sxs-lookup"><span data-stu-id="38ea2-137">If a user is a member of at least one team that has descendants in the hierarchy, that user can publish to those descendants without being a member of all teams they want to publish to.</span></span>
* <span data-ttu-id="38ea2-138">如果使用者是階層中至少一個團隊的成員，但不是階層中有後代的任何小組成員，該使用者就能查看並從組織中接收已發佈的內容。</span><span class="sxs-lookup"><span data-stu-id="38ea2-138">If a user is a member of a least one team in the hierarchy but isn't a member of any team with descendants in the hierarchy, that user can see and receive published content from their organization.</span></span>
* <span data-ttu-id="38ea2-139">如果使用者不是階層中任何小組的成員，該使用者就不會看到任何與發佈相關的功能。</span><span class="sxs-lookup"><span data-stu-id="38ea2-139">If a user isn't a member of any team in the hierarchy, that user won't see any publishing-related functionality.</span></span>

### <a name="guidelines"></a><span data-ttu-id="38ea2-140">相關</span><span class="sxs-lookup"><span data-stu-id="38ea2-140">Guidelines</span></span>

* <span data-ttu-id="38ea2-141">每個組織只能套用一個階層檔案。</span><span class="sxs-lookup"><span data-stu-id="38ea2-141">There can only be one hierarchy file applied per organization.</span></span> <span data-ttu-id="38ea2-142">不過，您可以將組織的不同部分，與單一 CSV 檔案中不同的節點階層結構組成。</span><span class="sxs-lookup"><span data-stu-id="38ea2-142">However, you can include different parts of your organization together as distinct hierarchies of nodes within one CSV file.</span></span> <span data-ttu-id="38ea2-143">例如，Contoso 製藥具有藥房根節點和零售根節點。</span><span class="sxs-lookup"><span data-stu-id="38ea2-143">For example, Contoso Pharmaceuticals has a Pharmacy root node and a Retail root node.</span></span> <span data-ttu-id="38ea2-144">兩個根節點都有多列後代，且兩者之間沒有任何交疊。</span><span class="sxs-lookup"><span data-stu-id="38ea2-144">Both root nodes have multiple rows of descendants and there's no overlap between them.</span></span>
* <span data-ttu-id="38ea2-145">只有葉節點可以是出版物的收件者。</span><span class="sxs-lookup"><span data-stu-id="38ea2-145">Only leaf nodes can be recipients of a publication.</span></span> <span data-ttu-id="38ea2-146">階層中的其他節點對於選取出版物的收件者很有説明。</span><span class="sxs-lookup"><span data-stu-id="38ea2-146">Other nodes in the hierarchy are helpful for selecting recipients of a publication.</span></span>
* <span data-ttu-id="38ea2-147">小組只能在階層中表示一次。</span><span class="sxs-lookup"><span data-stu-id="38ea2-147">A team can only be represented one time in a hierarchy.</span></span>
* <span data-ttu-id="38ea2-148">階層最多可以包含15000節點。</span><span class="sxs-lookup"><span data-stu-id="38ea2-148">A hierarchy can contain up to 15,000 nodes.</span></span> <span data-ttu-id="38ea2-149">我們打算與客戶合作，為較大的組織增加此限制。</span><span class="sxs-lookup"><span data-stu-id="38ea2-149">We plan to work with customers to raise this limit for larger organizations.</span></span>

### <a name="example-hierarchy"></a><span data-ttu-id="38ea2-150">層次結構範例</span><span class="sxs-lookup"><span data-stu-id="38ea2-150">Example hierarchy</span></span>

<span data-ttu-id="38ea2-151">例如，在下列階層、召回、通訊和人力資源中，您可以將工作發佈到階層中的每個底層節點 (團隊) ，但東北區域只能將工作發佈至紐約書店和波士頓商店小組。</span><span class="sxs-lookup"><span data-stu-id="38ea2-151">For example, in the following hierarchy, Recall, Communications, and HR can publish tasks to every bottom node (team) in the hierarchy, but Northeast Zone can only publish tasks to the New York Store and Boston Store teams.</span></span> <span data-ttu-id="38ea2-152">[範例階層] 可讓 [召回]、[通訊] 和 [人力資源] 群組發佈適用于整個公司的工作，例如 CEO 中的福利資訊或訊息。</span><span class="sxs-lookup"><span data-stu-id="38ea2-152">The example hierarchy allows the Recall, Communications, and HR groups to publish tasks that apply to the entire company, such as benefits information or messages from the CEO.</span></span> <span data-ttu-id="38ea2-153">東北區域可以發佈工作，例如人事排程、天氣資訊等，只適用于紐約書店與波士頓商店團隊。</span><span class="sxs-lookup"><span data-stu-id="38ea2-153">Northeast Zone can publish tasks like personnel scheduling, weather information, and so on, only to the New York Store and Boston Store teams.</span></span>

![小組階層範例](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a><span data-ttu-id="38ea2-155">建立階層</span><span class="sxs-lookup"><span data-stu-id="38ea2-155">Create your hierarchy</span></span>

> [!NOTE]
> <span data-ttu-id="38ea2-156">本文的其餘部分將討論在向收件者團隊發佈任務的內容中設定小組階層。</span><span class="sxs-lookup"><span data-stu-id="38ea2-156">The remainder of this article discusses setting up a team hierarchy in the context of publishing tasks to recipient teams.</span></span> <span data-ttu-id="38ea2-157">請參閱 [在團隊中管理貴組織的 [工作] app](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) ，以取得 [任務發佈] （如果啟用的話）。</span><span class="sxs-lookup"><span data-stu-id="38ea2-157">Refer to [Manage the Tasks app for your organization in Teams](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) for an overview of the Tasks app, where task publishing appears when enabled.</span></span>

<span data-ttu-id="38ea2-158">定義階層的架構是以逗號分隔的值（ (CSV) 檔案）為基礎。</span><span class="sxs-lookup"><span data-stu-id="38ea2-158">The schema that defines your hierarchy is based on a comma-separated values (CSV) file.</span></span> <span data-ttu-id="38ea2-159">CSV 檔案中的每個資料列都會對應至團隊階層中的一個節點。</span><span class="sxs-lookup"><span data-stu-id="38ea2-159">Each row in the CSV file corresponds to one node within the hierarchy of teams.</span></span> <span data-ttu-id="38ea2-160">每個資料列都包含針對階層中的節點命名的資訊（選擇性地將其連結至團隊），並包含可在支援它之應用程式中用來篩選小組的屬性。</span><span class="sxs-lookup"><span data-stu-id="38ea2-160">Each row contains information that names the node within the hierarchy, optionally links it to a team, and includes attributes that can be used to filter teams in apps that support it.</span></span>

<span data-ttu-id="38ea2-161">您也可以定義 **bucket**，發佈小組可以用來組織傳送給收件者小組的內容，讓他們更容易查看、排序及專注于相關內容。</span><span class="sxs-lookup"><span data-stu-id="38ea2-161">You can also define **buckets**, which are categories that the publishing team can use to organize content sent to recipient teams to make it easier for them to view, sort, and focus on relevant content.</span></span>

### <a name="add-required-columns"></a><span data-ttu-id="38ea2-162">新增必要的欄</span><span class="sxs-lookup"><span data-stu-id="38ea2-162">Add required columns</span></span>

<span data-ttu-id="38ea2-163">CSV 檔案必須包含下列三個數據行，並以下列順序從第一欄開始。</span><span class="sxs-lookup"><span data-stu-id="38ea2-163">The CSV file must contain the following three columns, in the following order, starting at the first column.</span></span> <span data-ttu-id="38ea2-164">若要接收工作，節點必須連結至團隊。</span><span class="sxs-lookup"><span data-stu-id="38ea2-164">A node must be linked to a team for it to receive tasks.</span></span>

| <span data-ttu-id="38ea2-165">欄名稱</span><span class="sxs-lookup"><span data-stu-id="38ea2-165">Column name</span></span>   | <span data-ttu-id="38ea2-166">必要</span><span class="sxs-lookup"><span data-stu-id="38ea2-166">Required</span></span> | <span data-ttu-id="38ea2-167">描述</span><span class="sxs-lookup"><span data-stu-id="38ea2-167">Description</span></span>   |
----------------|----------|---------------|
| <span data-ttu-id="38ea2-168">DisplayName</span><span class="sxs-lookup"><span data-stu-id="38ea2-168">DisplayName</span></span>    | <span data-ttu-id="38ea2-169">是</span><span class="sxs-lookup"><span data-stu-id="38ea2-169">Yes</span></span>      | <span data-ttu-id="38ea2-170">此欄位是節點的名稱。</span><span class="sxs-lookup"><span data-stu-id="38ea2-170">This field is the name of the node.</span></span> <span data-ttu-id="38ea2-171">名稱最多可以有100個字元，且只包含字元 a-z、a-z 及0-9。</span><span class="sxs-lookup"><span data-stu-id="38ea2-171">The name can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9.</span></span> <span data-ttu-id="38ea2-172">節點名稱必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="38ea2-172">Node names must be unique.</span></span> |
| <span data-ttu-id="38ea2-173">ParentName</span><span class="sxs-lookup"><span data-stu-id="38ea2-173">ParentName</span></span>    | <span data-ttu-id="38ea2-174">是</span><span class="sxs-lookup"><span data-stu-id="38ea2-174">Yes</span></span>       | <span data-ttu-id="38ea2-175">這是父節點的名稱。</span><span class="sxs-lookup"><span data-stu-id="38ea2-175">This is the name of the parent node.</span></span> <span data-ttu-id="38ea2-176">您在此處指定的值必須與父節點的 [ **DisplayName** ] 欄位中的值完全相符。</span><span class="sxs-lookup"><span data-stu-id="38ea2-176">The value you specify here must match the value in the **DisplayName** field of the parent node exactly.</span></span> <span data-ttu-id="38ea2-177">如果您想要新增一個以上的父節點，請使用分號分隔每個父節點名稱 (; ) 。</span><span class="sxs-lookup"><span data-stu-id="38ea2-177">If you want to add more than one parent node, separate each parent node name with a semicolon (;).</span></span> <span data-ttu-id="38ea2-178">您最多可以新增25個父節點，且每個父節點名稱最多可以有2500個字元。</span><span class="sxs-lookup"><span data-stu-id="38ea2-178">You can add up to 25 parent nodes, and each parent node name can be up to 2500 characters long.</span></span> <span data-ttu-id="38ea2-179">只有當父節點是根節點時，節點才能有多個父節點。</span><span class="sxs-lookup"><span data-stu-id="38ea2-179">A node can have multiple parent nodes only if the parent nodes are root nodes.</span></span>   <br><br><span data-ttu-id="38ea2-180">**重要** 請小心不要建立一個迴圈，層次結構中的上層上方會參照階層較低的子節點。</span><span class="sxs-lookup"><span data-stu-id="38ea2-180">**IMPORTANT** Be careful not to create a loop where a parent higher up in the hierarchy references a child node lower in the hierarchy.</span></span> <span data-ttu-id="38ea2-181">不支援這種情況。</span><span class="sxs-lookup"><span data-stu-id="38ea2-181">This isn't supported.</span></span> |
| <span data-ttu-id="38ea2-182">TeamId</span><span class="sxs-lookup"><span data-stu-id="38ea2-182">TeamId</span></span>        | <span data-ttu-id="38ea2-183">是，如果團隊發佈任務或從父節點接收工作</span><span class="sxs-lookup"><span data-stu-id="38ea2-183">Yes, if the team publishes tasks or receives tasks from a parent node</span></span>       | <span data-ttu-id="38ea2-184">這包含您要將節點連結至其中的團隊識別碼。</span><span class="sxs-lookup"><span data-stu-id="38ea2-184">This contains the ID of the team you want to link a node to.</span></span> <span data-ttu-id="38ea2-185">每個節點必須參照唯一的團隊，所以每個 TeamId 值在階層檔案中可能只會出現一次。</span><span class="sxs-lookup"><span data-stu-id="38ea2-185">Each node must refer to a unique team, so each TeamId value may appear only once in the hierarchy file.</span></span> <span data-ttu-id="38ea2-186">若要取得您想要將節點連結至其中團隊的識別碼，請執行下列 PowerShell 命令： `Get-Team | Export-Csv TeamList.csv` 。</span><span class="sxs-lookup"><span data-stu-id="38ea2-186">To get the ID of a team you want to link a node to, run the following PowerShell command: `Get-Team | Export-Csv TeamList.csv`.</span></span> <span data-ttu-id="38ea2-187">這個命令會列出貴組織中的小組，並包含每個團隊的名稱和識別碼。</span><span class="sxs-lookup"><span data-stu-id="38ea2-187">This command lists the teams in your organization and includes the name and ID for each team.</span></span> <span data-ttu-id="38ea2-188">找出您要連結的團隊名稱，然後將識別碼複製到此欄位。</span><span class="sxs-lookup"><span data-stu-id="38ea2-188">Find the name of the team you want to link to, and then copy the ID into this field.</span></span>|

> [!NOTE]
> <span data-ttu-id="38ea2-189">如果節點不是根節點或葉節點，而且您不需要團隊成員資格來授與發佈及報告相關的許可權，您可以將 TeamId 留白。</span><span class="sxs-lookup"><span data-stu-id="38ea2-189">If a node isn't a root node or a leaf node and you don't need the team membership to grant the corresponding permissions for publishing and reporting, you can leave the TeamId blank.</span></span> <span data-ttu-id="38ea2-190">此方法可用於在選擇收件者團隊時新增更多細微性，或在沒有相對應的小組的情況下查看完成報告。</span><span class="sxs-lookup"><span data-stu-id="38ea2-190">This method can be used to add more granularity when choosing recipient teams or for viewing completion reports without having a corresponding team.</span></span>

### <a name="add-attribute-columns"></a><span data-ttu-id="38ea2-191">新增屬性欄</span><span class="sxs-lookup"><span data-stu-id="38ea2-191">Add attribute columns</span></span>

<span data-ttu-id="38ea2-192">在您新增三個必要的資料行之後，您可以新增選用的屬性欄。</span><span class="sxs-lookup"><span data-stu-id="38ea2-192">After you add the three required columns, you can add optional attribute columns.</span></span> <span data-ttu-id="38ea2-193">這些屬性可用來篩選節點，讓您可以更輕鬆地選取您想要發佈任務的專案。</span><span class="sxs-lookup"><span data-stu-id="38ea2-193">These attributes can be used to filter nodes so that you can more easily select the ones you want to publish tasks to.</span></span> <span data-ttu-id="38ea2-194">有兩種方式可以定義您的屬性，這要視屬性的值是否相互排斥而定。</span><span class="sxs-lookup"><span data-stu-id="38ea2-194">There are two ways to define your attributes, depending on whether values for that attribute are mutually exclusive.</span></span>

|<span data-ttu-id="38ea2-195">新增屬性的方法</span><span class="sxs-lookup"><span data-stu-id="38ea2-195">Ways to add attributes</span></span>|<span data-ttu-id="38ea2-196">描述</span><span class="sxs-lookup"><span data-stu-id="38ea2-196">Description</span></span> |<span data-ttu-id="38ea2-197">範例</span><span class="sxs-lookup"><span data-stu-id="38ea2-197">Example</span></span>  |
|---|---------|---------|
|<span data-ttu-id="38ea2-198">如果屬性的值相互排斥，您指定的資料行名稱就會變成屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="38ea2-198">If the values for an attribute are mutually exclusive, the column name you specify becomes the name of the attribute.</span></span>|<span data-ttu-id="38ea2-199">每個資料列都可以包含該屬性的一個值，每個屬性欄最多可以有50個唯一值。</span><span class="sxs-lookup"><span data-stu-id="38ea2-199">Each row can contain one value for that attribute, and each attribute column can have up to 50 unique values.</span></span> <span data-ttu-id="38ea2-200">每個值最多可以長達100個字元。</span><span class="sxs-lookup"><span data-stu-id="38ea2-200">Each value can be up to 100 characters long.</span></span> <span data-ttu-id="38ea2-201">當您使用團隊目標階層選取收件者小組時，屬性欄中指定的屬性值集合將會顯示為該屬性的篩選值。</span><span class="sxs-lookup"><span data-stu-id="38ea2-201">The set of attribute values you specify in the attribute column will be displayed as filter values for that attribute when selecting recipient teams using the team targeting hierarchy.</span></span>|<span data-ttu-id="38ea2-202">您希望使用者能夠依版面配置篩選儲存。</span><span class="sxs-lookup"><span data-stu-id="38ea2-202">You want users to be able to filter stores by layout.</span></span> <span data-ttu-id="38ea2-203">這個屬性的值是互斥的，因為書店只能有一個版面配置。</span><span class="sxs-lookup"><span data-stu-id="38ea2-203">The values for this attribute are mutually exclusive because a store can have only one layout.</span></span> <br><br><span data-ttu-id="38ea2-204">若要新增屬性來依版面配置篩選儲存，請新增一個名為 [書店版面配置] 的欄。</span><span class="sxs-lookup"><span data-stu-id="38ea2-204">To add an attribute to filter stores by layout, add a column named Store layout.</span></span> <span data-ttu-id="38ea2-205">在這個範例中，Store layout 屬性的值為 Compact、Standard 及大型。</span><span class="sxs-lookup"><span data-stu-id="38ea2-205">In this example, values for the Store layout attribute are Compact, Standard, and Large.</span></span>
|<span data-ttu-id="38ea2-206">如果您需要指示屬性的多個值，且這些值不是互斥的，請使用 **AttributeName： UniqueValue** 格式的欄名稱。</span><span class="sxs-lookup"><span data-stu-id="38ea2-206">If you need to indicate multiple values for an attribute and the values aren't mutually exclusive, use the **AttributeName:UniqueValue** format for the column names.</span></span> <br><br><span data-ttu-id="38ea2-207">**重要** 請務必使用英文專用冒號 (： ) 為 unicode，不支援做為屬性欄分隔符號。</span><span class="sxs-lookup"><span data-stu-id="38ea2-207">**IMPORTANT** Make sure to use the English-only colon (:) as unicode isn't supported as an attribute column delimiter.</span></span> |<span data-ttu-id="38ea2-208">冒號 ( 之前的文字字串： ) 成為屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="38ea2-208">The text string before the colon (:) becomes the name of the attribute.</span></span> <span data-ttu-id="38ea2-209">所有的資料列都包含相同的文字字串，且在冒號 ( 之前： ) 會分組成 [篩選] 功能表中的某個區段。</span><span class="sxs-lookup"><span data-stu-id="38ea2-209">All columns that contain the same text string before the colons (:) are grouped together into a section in the filtering menu.</span></span> <span data-ttu-id="38ea2-210">冒號後面的每個字串都會成為該節的值。</span><span class="sxs-lookup"><span data-stu-id="38ea2-210">Each of the strings after the colon become the values for that section.</span></span><br><br><span data-ttu-id="38ea2-211">每個資料列的值都可以是 0 (零) 或1（針對該屬性）。</span><span class="sxs-lookup"><span data-stu-id="38ea2-211">Each row can have a value of 0 (zero) or 1 for that attribute.</span></span> <span data-ttu-id="38ea2-212">值為0表示屬性不會套用至節點，值1表示屬性適用于該節點。</span><span class="sxs-lookup"><span data-stu-id="38ea2-212">A value of 0 means that the attribute doesn't apply to the node and a value of 1 means that the attribute applies to that node.</span></span>|<span data-ttu-id="38ea2-213">您希望使用者能夠依部門篩選商店。</span><span class="sxs-lookup"><span data-stu-id="38ea2-213">You want users to be able to filter stores by department.</span></span> <span data-ttu-id="38ea2-214">商店可以有多個部門，所以這個屬性的值不是互相排斥的。</span><span class="sxs-lookup"><span data-stu-id="38ea2-214">A store can have multiple departments and so the values for this attribute aren't mutually exclusive.</span></span><br><br><span data-ttu-id="38ea2-215">在這個範例中，我們將新增部門：服裝、部門：電子產品、部門：食物、部門：家用和花園、部門：體育產品是屬性欄。</span><span class="sxs-lookup"><span data-stu-id="38ea2-215">In this example, we add Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting goods as attribute columns.</span></span> <span data-ttu-id="38ea2-216">[部門] 會成為屬性名稱，而且使用者可以透過衣物、電子、食品、家用和花園以及體育用品部門來篩選。</span><span class="sxs-lookup"><span data-stu-id="38ea2-216">Departments becomes the attribute name and users can filter by the Clothing, Electronics, Foods, Home and Garden, and Sporting goods departments.</span></span>|

<span data-ttu-id="38ea2-217">當您新增屬性欄時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="38ea2-217">When you add an attribute column, keep the following in mind:</span></span>

* <span data-ttu-id="38ea2-218">您指定的欄名或您在冒號 ( 之前指定的欄名稱： ) 成為屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="38ea2-218">The column name you specify or the column name that you specify before the colon (:) becomes the name of the attribute.</span></span> <span data-ttu-id="38ea2-219">此值將會顯示在使用階層的團隊 app 中。</span><span class="sxs-lookup"><span data-stu-id="38ea2-219">This value will be displayed in the Teams apps that use the hierarchy.</span></span>
* <span data-ttu-id="38ea2-220">您最多可以在層次結構中擁有50屬性欄。</span><span class="sxs-lookup"><span data-stu-id="38ea2-220">You can have up to 50 attribute columns in your hierarchy.</span></span>
* <span data-ttu-id="38ea2-221">資料行名稱最多可以有100個字元，且只包含字元 a-z、a-z 以及0-9 及空格。</span><span class="sxs-lookup"><span data-stu-id="38ea2-221">The column name can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9, and spaces.</span></span> <span data-ttu-id="38ea2-222">欄名必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="38ea2-222">Column names must be unique.</span></span>

### <a name="add-bucket-columns"></a><span data-ttu-id="38ea2-223">新增 bucket 欄</span><span class="sxs-lookup"><span data-stu-id="38ea2-223">Add bucket columns</span></span>

<span data-ttu-id="38ea2-224">您可以新增 bucket 欄來建立桶，該 bucket 是群組，可將任務組織成哪些專案。</span><span class="sxs-lookup"><span data-stu-id="38ea2-224">You can add bucket columns to create buckets, which are groupings into which tasks can be organized.</span></span> <span data-ttu-id="38ea2-225">每個 bucket 都會在 CSV 檔案中取得自己的欄。</span><span class="sxs-lookup"><span data-stu-id="38ea2-225">Each bucket gets its own column in the CSV file.</span></span> <span data-ttu-id="38ea2-226">您建立的 bucket 會提供給發佈小組使用。</span><span class="sxs-lookup"><span data-stu-id="38ea2-226">The buckets you create are made available to the publishing team.</span></span> <span data-ttu-id="38ea2-227">發佈小組可以使用這些 bucket 來為收件者小組分類工作。</span><span class="sxs-lookup"><span data-stu-id="38ea2-227">The publishing team can then use these buckets to categorize tasks for the recipient teams.</span></span> <span data-ttu-id="38ea2-228">如果小組中不存在某個 bucket，則會在發佈任務時，根據需要建立 bucket。</span><span class="sxs-lookup"><span data-stu-id="38ea2-228">If a bucket doesn't already exist on a team, buckets are created on-demand when tasks are published.</span></span>

<span data-ttu-id="38ea2-229">只要將工作專案集中歸類一次，發佈小組就可以為接收工作清單的數十個、成百上千個或數千個收件者小組預先組織工作清單。</span><span class="sxs-lookup"><span data-stu-id="38ea2-229">By categorizing the work items one time centrally, the publishing team can pre-organize the task list for all the tens, hundreds, or thousands of recipient teams that receive the task list.</span></span> <span data-ttu-id="38ea2-230">然後，收件者小組可以依 bucket 來排序及篩選其任務，將焦點放在與他們的工作最相關的區域上。</span><span class="sxs-lookup"><span data-stu-id="38ea2-230">The recipient teams can then sort and filter their tasks by bucket to focus on the area most relevant to their work.</span></span>

<span data-ttu-id="38ea2-231">當您新增 [桶] 欄時，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="38ea2-231">When you add a bucket column, note the following:</span></span>

* <span data-ttu-id="38ea2-232">欄名稱會變成 bucket 的名稱。</span><span class="sxs-lookup"><span data-stu-id="38ea2-232">The column name becomes the name of the bucket.</span></span> <span data-ttu-id="38ea2-233">您指定的每個 bucket 都會出現在使用階層之小組 app 的 Bucket 清單中。</span><span class="sxs-lookup"><span data-stu-id="38ea2-233">Each bucket you specify will appear in the Buckets list in the Teams apps that use the hierarchy.</span></span>
* <span data-ttu-id="38ea2-234">我們建議您不要在 bucket 名稱中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="38ea2-234">We recommend that you don't include sensitive information in bucket names.</span></span> <span data-ttu-id="38ea2-235">目前，發佈團隊在建立後無法透過發佈來移除 bucket。</span><span class="sxs-lookup"><span data-stu-id="38ea2-235">At this time, publishing teams can't remove a bucket through publishing after it's created.</span></span>
* <span data-ttu-id="38ea2-236">欄名前面必須是 # 號 ( # ) 。</span><span class="sxs-lookup"><span data-stu-id="38ea2-236">The column name must be preceded by a hashtag (#).</span></span> <span data-ttu-id="38ea2-237">它最多可以包含100個字元，且只能包含字元 a-z、a-z 和0-9。</span><span class="sxs-lookup"><span data-stu-id="38ea2-237">It can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9.</span></span> <span data-ttu-id="38ea2-238">例如，#Operations 並 #Frozen 商品。</span><span class="sxs-lookup"><span data-stu-id="38ea2-238">For example, #Operations and #Frozen Goods.</span></span>
* <span data-ttu-id="38ea2-239">階層最多可包含25個 bucket 欄。</span><span class="sxs-lookup"><span data-stu-id="38ea2-239">A hierarchy may contain up to 25 bucket columns.</span></span> <span data-ttu-id="38ea2-240">我們打算與客戶合作，為較大的組織增加此限制。</span><span class="sxs-lookup"><span data-stu-id="38ea2-240">We plan to work with customers to increase this limit for larger organizations.</span></span>

### <a name="example"></a><span data-ttu-id="38ea2-241">範例</span><span class="sxs-lookup"><span data-stu-id="38ea2-241">Example</span></span>

<span data-ttu-id="38ea2-242">以下是要建立以支援上一個影像所示階層之架構 CSV 檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="38ea2-242">Here's an example of a schema CSV file that would be created to support the hierarchy shown in the previous image.</span></span> <span data-ttu-id="38ea2-243">此架構包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="38ea2-243">This schema contains the following:</span></span>

* <span data-ttu-id="38ea2-244">三個必要的欄，名為 `TargetName` 、 `ParentName` 和 `TeamId`</span><span class="sxs-lookup"><span data-stu-id="38ea2-244">Three required columns named `TargetName`, `ParentName`, and `TeamId`</span></span>
* <span data-ttu-id="38ea2-245">名為 `Store layout` 、和的三個屬性欄 `Departments:Clothing``Departments:Foods`</span><span class="sxs-lookup"><span data-stu-id="38ea2-245">Three attribute columns named `Store layout`, `Departments:Clothing`, and `Departments:Foods`</span></span>
* <span data-ttu-id="38ea2-246">名為 `Fresh Foods` 、 `Frozen Foods` 和的三個 bucket 欄 `Women's Wear`</span><span class="sxs-lookup"><span data-stu-id="38ea2-246">Three bucket columns named `Fresh Foods`, `Frozen Foods`, and `Women's Wear`</span></span>

<span data-ttu-id="38ea2-247">`Store layout`屬性具有值，其中包含 `Compact` 、 `Standard` 和 `Large` 。</span><span class="sxs-lookup"><span data-stu-id="38ea2-247">The `Store layout` attribute has values that include `Compact`, `Standard`, and `Large`.</span></span> <span data-ttu-id="38ea2-248">`Departments`屬性欄可以設定為 `0` (零) 或的值 `1` 。</span><span class="sxs-lookup"><span data-stu-id="38ea2-248">The `Departments` attribute columns can be set to a value of `0` (zero) or `1`.</span></span> <span data-ttu-id="38ea2-249">`Store`版面配置和 `Departments` 屬性不會顯示在上述影像中。</span><span class="sxs-lookup"><span data-stu-id="38ea2-249">The `Store` layout and `Departments` attributes aren't shown in the image above.</span></span> <span data-ttu-id="38ea2-250">我們在這裡新增這些專案，以協助示範如何將屬性新增至節點專案。</span><span class="sxs-lookup"><span data-stu-id="38ea2-250">They're added here to help show how attributes can be added to node entries.</span></span> <span data-ttu-id="38ea2-251">這種情況對於三個桶欄都是一樣的。</span><span class="sxs-lookup"><span data-stu-id="38ea2-251">The same is true for the three bucket columns.</span></span>

```CSV
"TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear"
"Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,"
"Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,"
"HR,,,,,,,,,,"
"East Regional Office,,,,,,,,,,"
"West Regional Office,,,,,,,,,,"
"Northeast Zone,East Regional Office,,,,,,,,"
"Southeast Zone,East Regional Office,,,,,,,,"
"New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,"
"Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,"
"Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,"
"New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,"
"Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,"
"Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,"
```

## <a name="apply-your-hierarchy"></a><span data-ttu-id="38ea2-252">套用您的階層</span><span class="sxs-lookup"><span data-stu-id="38ea2-252">Apply your hierarchy</span></span>

<span data-ttu-id="38ea2-253">在架構 CSV 檔案中定義階層之後，您就可以將其上傳至團隊。</span><span class="sxs-lookup"><span data-stu-id="38ea2-253">After you've defined your hierarchy in the schema CSV file, you're ready to upload it to Teams.</span></span> <span data-ttu-id="38ea2-254">若要這樣做，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="38ea2-254">To do this, run the following command.</span></span> <span data-ttu-id="38ea2-255">您必須是全域管理員或團隊服務系統管理員，才能執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="38ea2-255">You must be a global admin or Teams service admin to do this step.</span></span>

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a><span data-ttu-id="38ea2-256">更新您的階層</span><span class="sxs-lookup"><span data-stu-id="38ea2-256">Update your hierarchy</span></span>

<span data-ttu-id="38ea2-257">您可以使用與上述相同的 PowerShell 命令，上傳新的階層來取代舊的階層。</span><span class="sxs-lookup"><span data-stu-id="38ea2-257">You can upload a new hierarchy to replace the old one using the same PowerShell command as above.</span></span> <span data-ttu-id="38ea2-258">每次上傳新的階層時，都會取代先前的階層。</span><span class="sxs-lookup"><span data-stu-id="38ea2-258">Each time you upload a new hierarchy, it replaces the previous hierarchy.</span></span>

### <a name="check-the-status-of-your-hierarchy"></a><span data-ttu-id="38ea2-259">檢查階層的狀態</span><span class="sxs-lookup"><span data-stu-id="38ea2-259">Check the status of your hierarchy</span></span>

<span data-ttu-id="38ea2-260">您可以執行下列命令，以檢查階層上傳的狀態。</span><span class="sxs-lookup"><span data-stu-id="38ea2-260">You can run the following command to check the status of your hierarchy upload.</span></span>

```powershell
Get-TeamTargetingHierarchyStatus
```

<span data-ttu-id="38ea2-261">此命令會傳回下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="38ea2-261">The command will return the following fields:</span></span>

<span data-ttu-id="38ea2-262">域</span><span class="sxs-lookup"><span data-stu-id="38ea2-262">Field</span></span>|<span data-ttu-id="38ea2-263">描述</span><span class="sxs-lookup"><span data-stu-id="38ea2-263">Description</span></span>
-----|------------
<span data-ttu-id="38ea2-264">標識號</span><span class="sxs-lookup"><span data-stu-id="38ea2-264">Id</span></span> | <span data-ttu-id="38ea2-265">上傳的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="38ea2-265">The unique ID for the upload.</span></span>
<span data-ttu-id="38ea2-266">狀態值</span><span class="sxs-lookup"><span data-stu-id="38ea2-266">Status</span></span> | <span data-ttu-id="38ea2-267">上傳狀態。</span><span class="sxs-lookup"><span data-stu-id="38ea2-267">Upload status.</span></span> <span data-ttu-id="38ea2-268">值包括 **啟動**、 **驗證**、 **成功** 和 **失敗**</span><span class="sxs-lookup"><span data-stu-id="38ea2-268">Values include **Starting**, **Validating**, **Successful**, and **Failed**</span></span>
<span data-ttu-id="38ea2-269">ErrorDetails</span><span class="sxs-lookup"><span data-stu-id="38ea2-269">ErrorDetails</span></span> | <span data-ttu-id="38ea2-270">詳細資料（如果有上傳錯誤的話）。</span><span class="sxs-lookup"><span data-stu-id="38ea2-270">Details if there's an upload error.</span></span> <span data-ttu-id="38ea2-271">如需錯誤詳細資料的詳細資訊，請參閱疑難排解一節。</span><span class="sxs-lookup"><span data-stu-id="38ea2-271">For more information about the error details, see the Troubleshooting section.</span></span> <span data-ttu-id="38ea2-272">如果沒有錯誤，此欄位為空白。</span><span class="sxs-lookup"><span data-stu-id="38ea2-272">If there's no error, this field is blank.</span></span>
<span data-ttu-id="38ea2-273">LastUpdatedAt</span><span class="sxs-lookup"><span data-stu-id="38ea2-273">LastUpdatedAt</span></span> | <span data-ttu-id="38ea2-274">上次更新檔案的時間戳記和日期。</span><span class="sxs-lookup"><span data-stu-id="38ea2-274">Timestamp and date of when the file was last updated.</span></span>
<span data-ttu-id="38ea2-275">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="38ea2-275">LastModifiedBy</span></span> | <span data-ttu-id="38ea2-276">上次修改檔案的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="38ea2-276">The ID of the last user who modified the file.</span></span>
<span data-ttu-id="38ea2-277">副檔名</span><span class="sxs-lookup"><span data-stu-id="38ea2-277">FileName</span></span> | <span data-ttu-id="38ea2-278">CSV 的檔案名。</span><span class="sxs-lookup"><span data-stu-id="38ea2-278">The file name of the CSV.</span></span>

## <a name="remove-your-hierarchy"></a><span data-ttu-id="38ea2-279">移除階層</span><span class="sxs-lookup"><span data-stu-id="38ea2-279">Remove your hierarchy</span></span>

<span data-ttu-id="38ea2-280">如果您想要立即停用貴組織中所有使用者的 [ **已發佈的清單** ] 索引標籤，您可以移除您的階層。</span><span class="sxs-lookup"><span data-stu-id="38ea2-280">If you want to immediately disable the **Published lists** tab for all users in your organization, you can remove your hierarchy.</span></span> <span data-ttu-id="38ea2-281">使用者無法存取 [ **已發佈的清單** ] 索引標籤或 [索引標籤] 上的任何功能。 這包括建立新工作清單以進行發佈、存取草稿清單、發佈、取消發佈及重複清單以及查看報表的功能。</span><span class="sxs-lookup"><span data-stu-id="38ea2-281">Users won't have access to the **Published lists** tab or any of the functionalities on the tab.  This includes the ability to create new task lists to publish, access draft lists, publish, unpublish, and duplicate lists, and view reporting.</span></span> <span data-ttu-id="38ea2-282">移除階層後，就不會取消發佈先前發佈的工作。</span><span class="sxs-lookup"><span data-stu-id="38ea2-282">Removing the hierarchy doesn't unpublish tasks that were previously published.</span></span> <span data-ttu-id="38ea2-283">這些工作仍可供收件者團隊完成。</span><span class="sxs-lookup"><span data-stu-id="38ea2-283">These tasks will remain available for recipient teams to complete.</span></span>

<span data-ttu-id="38ea2-284">若要移除階層，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="38ea2-284">To remove your hierarchy, run the following command.</span></span> <span data-ttu-id="38ea2-285">您必須是系統管理員，才能執行這個步驟。</span><span class="sxs-lookup"><span data-stu-id="38ea2-285">You must be an admin to perform this step.</span></span>

```powershell
Remove-TeamTargetingHierarchy
```

<span data-ttu-id="38ea2-286">確認刪除時，狀態訊息仍會顯示先前的架構，但如果再次嘗試刪除，則會傳回物件為 null 的錯誤。</span><span class="sxs-lookup"><span data-stu-id="38ea2-286">When confirming deletion, the status message will still display the previous schema is present, although attempting to delete again returns an error that the object is null.</span></span>

## <a name="create-a-sample-hierarchy"></a><span data-ttu-id="38ea2-287">建立範例階層</span><span class="sxs-lookup"><span data-stu-id="38ea2-287">Create a sample hierarchy</span></span>

### <a name="install-the-teams-powershell-module"></a><span data-ttu-id="38ea2-288">安裝團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="38ea2-288">Install the Teams PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38ea2-289">若要執行此步驟，您必須從 [PowerShell 庫](https://www.powershellgallery.com/packages/MicrosoftTeams/)安裝並使用 [團隊 PowerShell 公用預覽] 模組。</span><span class="sxs-lookup"><span data-stu-id="38ea2-289">To perform this step, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="38ea2-290">如需如何安裝模組的步驟，請參閱 [安裝團隊 PowerShell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="38ea2-290">For steps on how to install the module, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

### <a name="sample-script"></a><span data-ttu-id="38ea2-291">範例腳本</span><span class="sxs-lookup"><span data-stu-id="38ea2-291">Sample script</span></span>

<span data-ttu-id="38ea2-292">下列腳本可用來建立小組，並將 .csv 檔案上傳到您的 Microsoft 團隊租使用者。</span><span class="sxs-lookup"><span data-stu-id="38ea2-292">The following script can be used to create the teams and upload a .csv file to your Microsoft Teams tenant.</span></span> <span data-ttu-id="38ea2-293">如果您已有階層，此腳本會將它取代。</span><span class="sxs-lookup"><span data-stu-id="38ea2-293">If you have an existing hierarchy, this script will replace it.</span></span>

#### <a name="create-teams-for-a-simple-hierarchy"></a><span data-ttu-id="38ea2-294">建立適用于簡單階層的團隊</span><span class="sxs-lookup"><span data-stu-id="38ea2-294">Create teams for a simple hierarchy</span></span>

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a><span data-ttu-id="38ea2-295">使用小組資料來建立以逗號分隔的輸出 (DisplayName、ParentName、TeamId) </span><span class="sxs-lookup"><span data-stu-id="38ea2-295">Use team data to create comma-separated output (DisplayName, ParentName, TeamId)</span></span>

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

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a><span data-ttu-id="38ea2-296">將輸出儲存至 [ **下載** ] 資料夾中的 .csv 檔案</span><span class="sxs-lookup"><span data-stu-id="38ea2-296">Save output to a .csv file in the **Downloads** folder</span></span>

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a><span data-ttu-id="38ea2-297">上傳階層</span><span class="sxs-lookup"><span data-stu-id="38ea2-297">Upload the hierarchy</span></span>

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a><span data-ttu-id="38ea2-298">疑難排解</span><span class="sxs-lookup"><span data-stu-id="38ea2-298">Troubleshooting</span></span>

### <a name="how-to-view-error-details"></a><span data-ttu-id="38ea2-299">如何查看錯誤詳細資料</span><span class="sxs-lookup"><span data-stu-id="38ea2-299">How to view error details</span></span>

<span data-ttu-id="38ea2-300">您可以執行下列命令，以瞭解導致錯誤的原因，並傳回錯誤詳細資料。</span><span class="sxs-lookup"><span data-stu-id="38ea2-300">You can run the following command to understand what is causing an error and return the error details.</span></span>

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a><span data-ttu-id="38ea2-301">您上傳架構 CSV 檔案時會收到錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="38ea2-301">You receive an error message when you upload your schema CSV file</span></span>

<span data-ttu-id="38ea2-302">記下錯誤訊息，因為它應該包含疑難排解資訊，以指出無法上傳架構的原因。</span><span class="sxs-lookup"><span data-stu-id="38ea2-302">Take note of the error message as it should include troubleshooting information to indicate why the schema couldn't be uploaded.</span></span> <span data-ttu-id="38ea2-303">根據錯誤訊息中的資訊，查看及編輯您的架構 CSV 檔案，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="38ea2-303">Review and edit your schema CSV file based on the information in the error message and then try again.</span></span>

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a><span data-ttu-id="38ea2-304">當您上傳架構 CSV 檔案時，會收到「錯誤： InvalidTeamId」錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="38ea2-304">You receive an "Error: InvalidTeamId" error message when you upload your schema CSV file</span></span>

<span data-ttu-id="38ea2-305">當您嘗試上傳架構 CSV 檔案時，您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="38ea2-305">When you try to upload your schema CSV file, you get the following error message:</span></span>

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

<span data-ttu-id="38ea2-306">請檢查以確定您的架構 CSV 檔案中的小組使用的是正確的 TeamId。</span><span class="sxs-lookup"><span data-stu-id="38ea2-306">Check to make sure that you're using the correct TeamId for the team in your schema CSV file.</span></span> <span data-ttu-id="38ea2-307">TeamId 應該與支援小組的 Microsoft 365 群組的群組識別碼相同。</span><span class="sxs-lookup"><span data-stu-id="38ea2-307">The TeamId should be the same as the Group ID of the Microsoft 365 group that backs the team.</span></span> <span data-ttu-id="38ea2-308">您可以在 Microsoft 團隊系統管理中心查詢團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="38ea2-308">You can look up the Group ID of the team in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="38ea2-309">在 [Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，前往 [**團隊**]  >  **管理團隊**。</span><span class="sxs-lookup"><span data-stu-id="38ea2-309">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams** > **Manage teams**.</span></span>
2. <span data-ttu-id="38ea2-310">如果表格中沒有顯示 [ **群組識別碼** ] 欄，請選取表格右上角的 [ **編輯欄** ]，然後開啟 [ **群組識別碼**]。</span><span class="sxs-lookup"><span data-stu-id="38ea2-310">If the **Group ID** column isn't displayed in the table, select **Edit columns** in the upper-right corner of the table, and then turn on **Group ID**.</span></span>
3. <span data-ttu-id="38ea2-311">在清單中尋找小組，然後找到 [群組識別碼]。</span><span class="sxs-lookup"><span data-stu-id="38ea2-311">Find the team in the list, and then locate the Group ID.</span></span>

<span data-ttu-id="38ea2-312">確認您架構 CSV 檔案中的 TeamId 與顯示在 Microsoft 團隊系統管理中心的群組識別碼相符。</span><span class="sxs-lookup"><span data-stu-id="38ea2-312">Make sure that the TeamId in your schema CSV file matches the Group ID that's displayed in the Microsoft Teams admin center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="38ea2-313">相關主題</span><span class="sxs-lookup"><span data-stu-id="38ea2-313">Related topics</span></span>

* [<span data-ttu-id="38ea2-314">在團隊中管理貴組織的任務應用程式</span><span class="sxs-lookup"><span data-stu-id="38ea2-314">Manage the Tasks app for your organization in Teams</span></span>](manage-tasks-app.md)
* [<span data-ttu-id="38ea2-315">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="38ea2-315">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
