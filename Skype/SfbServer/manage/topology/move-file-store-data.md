---
title: 在商務用 Skype Server 中將檔案儲存資料移至新的檔案存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 如果您需要移除目前作為商務用 Skype Server 部署之檔案存放區的檔案伺服器，或如果您需要進行其他變更，以使目前的檔案存放庫無法使用，您必須先建立新的共用。 接著，您需要執行下列步驟：
ms.openlocfilehash: 91ba8393a958188e368ff3f8f5d2a85bcfcc1396
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888452"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="1ddb1-104">在商務用 Skype Server 中將檔案儲存資料移至新的檔案存放區</span><span class="sxs-lookup"><span data-stu-id="1ddb1-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="1ddb1-105">如果您需要移除目前作為商務用 Skype Server 部署之檔案存放區的檔案伺服器，或如果您需要進行其他變更，以使目前的檔案存放庫無法使用，您必須先建立新的共用。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="1ddb1-106">接著，您需要執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1ddb1-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="1ddb1-107">關閉使用您打算移除之檔案存放區的商務用 Skype 伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="1ddb1-108">在拓撲建立器中定義檔案存放區併發布變更，讓您的部署能使用新的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="1ddb1-109">將資料移至新的檔存放區。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="1ddb1-110">重新開機伺服器或服務。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="1ddb1-111">或者，移除舊的 [檔案共用] 和 [檔案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="1ddb1-112">將檔案儲存區資料從一個檔案存放區移至新的檔案存放區</span><span class="sxs-lookup"><span data-stu-id="1ddb1-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="1ddb1-113">以 RTCUniversersalServerAdmins 或 CsServerAdministrator 群組成員的身分登入電腦，其中安裝的是商務用 Skype 伺服器、系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="1ddb1-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1ddb1-115">在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="1ddb1-116">針對每個使用您打算移除之檔案存放區的控制器池、導演、標準版伺服器及前端池，請選取伺服器或池，按一下 [**動作**]，然後按一下 [**停止所有服務**]。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="1ddb1-117">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="1ddb1-118">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype server**]，然後按一下 [**商務用 skype server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="1ddb1-119">選取使用檔案存放區的伺服器或池，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1ddb1-119">Select a server or pool that uses the file store, and do the following:</span></span>

   <span data-ttu-id="1ddb1-120">是.</span><span class="sxs-lookup"><span data-stu-id="1ddb1-120">a.</span></span> <span data-ttu-id="1ddb1-121">以滑鼠右鍵按一下 [伺服器] 或 [池]，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-121">Right-click the server or pool, and then click **Edit Properties**.</span></span>

   <span data-ttu-id="1ddb1-122">乙.</span><span class="sxs-lookup"><span data-stu-id="1ddb1-122">b.</span></span> <span data-ttu-id="1ddb1-123">在 [**編輯屬性**] 的 [**關聯**] 底下，按一下 [檔案**存放**] 底下的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

   <span data-ttu-id="1ddb1-124">c-clip.</span><span class="sxs-lookup"><span data-stu-id="1ddb1-124">c.</span></span> <span data-ttu-id="1ddb1-125">在 [**定義新檔案存放區**] 的 [檔案**伺服器 FQDN**] 底下，輸入檔案伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="1ddb1-126">在 [檔案**共用**] 底下，輸入新檔案共用的資料夾名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="1ddb1-127">此步驟會定義要在拓撲建立器中使用的新檔存放區。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="1ddb1-128">您只需定義一次，不能針對每個伺服器定義。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-128">You define it only once, not for each server.</span></span> <span data-ttu-id="1ddb1-129">您必須先在已定義的檔案伺服器上建立已定義的檔案共用，才能發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="1ddb1-130">如需詳細資訊，請參閱[定義前端的檔案存放區](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-130">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

8. <span data-ttu-id="1ddb1-131">針對使用檔案存放區的每個伺服器或池，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1ddb1-131">For each server or pool that uses the file store, do the following:</span></span>

   <span data-ttu-id="1ddb1-132">是.</span><span class="sxs-lookup"><span data-stu-id="1ddb1-132">a.</span></span> <span data-ttu-id="1ddb1-133">以滑鼠右鍵按一下 [伺服器] 或 [池]，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-133">Right-click the server or pool, and then click **Edit properties**.</span></span>

   <span data-ttu-id="1ddb1-134">乙.</span><span class="sxs-lookup"><span data-stu-id="1ddb1-134">b.</span></span> <span data-ttu-id="1ddb1-135">在 [**編輯屬性**] 的 [**關聯**] 底下，選取 [檔案**存放區**] 中的新檔案共用，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

9. <span data-ttu-id="1ddb1-136">發佈拓撲，檢查 [複製狀態]，然後視需要執行商務用 Skype Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="1ddb1-137">如需詳細資訊，請參閱[移除 Lync server 和元件的一般程式](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-137">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

10. <span data-ttu-id="1ddb1-138">啟動命令提示字元：按一下 [**開始**]，按一下 [**執行**]，然後輸入 cmd.exe。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

11. <span data-ttu-id="1ddb1-139">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="1ddb1-139">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="1ddb1-140">/S 開關會複製到檔案、目錄及子目錄中。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="1ddb1-141">/XF 開關會跳過名為「會議」的任何檔案。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="1ddb1-142">使用/MT 開關的 [robocopy] 的目前版本，會以多個執行緒大幅增加複製速度。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="1ddb1-143">如果是/LOG 開關，請使用 C:\Logfiles\log.txt. 形式的目錄路徑和記錄檔案名</span><span class="sxs-lookup"><span data-stu-id="1ddb1-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="1ddb1-144">這個開關會建立位於指定位置的作業記錄檔。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-144">This switch creates a log file of operations at the named location.</span></span>

12. <span data-ttu-id="1ddb1-145">資料複製完成後，請在 [Lync Server 控制台] 中按一下 [**拓撲**]，然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

13. <span data-ttu-id="1ddb1-146">針對您停止服務的每個伺服器或池，選取伺服器或池子，按一下 [**動作**]，然後按一下 [**啟動所有服務**]。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

14. <span data-ttu-id="1ddb1-147">從拓撲中移除舊的檔案存放區，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-147">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="1ddb1-148">如需詳細資訊，請參閱[移除檔案存放區](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-148">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

15. <span data-ttu-id="1ddb1-149">可選登入包含您剛剛移除為本機管理員群組或網域系統管理員群組成員的檔案存放區的電腦，然後移除舊的檔案共用和目錄。</span><span class="sxs-lookup"><span data-stu-id="1ddb1-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ddb1-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1ddb1-150">See also</span></span>

[<span data-ttu-id="1ddb1-151">將伺服器重新指派至不同的檔案存放區</span><span class="sxs-lookup"><span data-stu-id="1ddb1-151">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="1ddb1-152">移除檔案存放區</span><span class="sxs-lookup"><span data-stu-id="1ddb1-152">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
