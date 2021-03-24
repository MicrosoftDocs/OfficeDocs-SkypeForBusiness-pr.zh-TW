---
title: 在商務用 Skype Server 中將檔案存放區資料移至新的檔案存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 如果您需要移除目前做為商務用 Skype 伺服器部署之檔案存放區的檔案伺服器，或者您需要進行其他變更，使目前的檔案存放區無法使用，您必須先建立新的共用。 接著，您必須執行下列步驟：
ms.openlocfilehash: a2870f024964a385852b7ecc781dbfb5647550b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093301"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="6f6cb-104">在商務用 Skype Server 中將檔案存放區資料移至新的檔案存放區</span><span class="sxs-lookup"><span data-stu-id="6f6cb-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="6f6cb-105">如果您需要移除目前做為商務用 Skype 伺服器部署之檔案存放區的檔案伺服器，或者您需要進行其他變更，使目前的檔案存放區無法使用，您必須先建立新的共用。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="6f6cb-106">接著，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6f6cb-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="6f6cb-107">關閉使用您計畫要移除之檔案存放區的商務用 Skype 伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="6f6cb-108">在拓撲產生器中定義檔案存放區，併發布變更，讓部署使用新的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="6f6cb-109">將資料移至新的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="6f6cb-110">重新開機伺服器或服務。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="6f6cb-111">（選用）移除舊的檔案共用和資料夾。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="6f6cb-112">將檔案存放區資料從一個檔案存放區移至新的檔案存放區</span><span class="sxs-lookup"><span data-stu-id="6f6cb-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="6f6cb-113">以 RTCUniversersalServerAdmins 的成員身分登入電腦，或以商務用 Skype 伺服器及系統管理工具安裝的 CsServerAdministrator 群組的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="6f6cb-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="6f6cb-115">在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **狀態**]。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="6f6cb-116">針對每個 Director 集區、Director、Standard Edition server 和前端集區（使用您計畫移除的檔案存放區），選取伺服器或集區，按一下 [ **動作**]，然後按一下 [ **停止所有服務**]。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="6f6cb-117">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="6f6cb-118">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 伺服器**]，然後按一下 [ **商務用 skype server 拓撲** 產生器]。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="6f6cb-119">選取使用檔案存放區的伺服器或集區，然後執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="6f6cb-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="6f6cb-120">以滑鼠右鍵按一下伺服器或集區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="6f6cb-121">在 [ **編輯屬性**] 的 [ **關聯**] 下，按一下 [檔案 **存放區**] 底下的 [ **新增**]</span><span class="sxs-lookup"><span data-stu-id="6f6cb-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="6f6cb-122">在 [ **定義新的檔案存放區**] 的 [檔案 **伺服器 FQDN**] 下，輸入檔案伺服器的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="6f6cb-123">在 [檔案 **共用**] 底下，輸入新檔共用的資料夾名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="6f6cb-124">這個步驟會定義新的檔案存放區，以供拓撲產生器使用。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="6f6cb-125">您只能將它定義一次，而不是針對每一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-125">You define it only once, not for each server.</span></span> <span data-ttu-id="6f6cb-126">在發行拓撲之前，您必須在定義的檔案伺服器上建立已定義的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="6f6cb-127">如需詳細資訊，請參閱[定義前端的檔案存放區](/previous-versions/office/communications/gg133895(v=ocs.14))。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-127">For details, see [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).</span></span>

11. <span data-ttu-id="6f6cb-128">針對每個使用檔案存放區的伺服器或集區，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="6f6cb-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="6f6cb-129">以滑鼠右鍵按一下伺服器或集區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="6f6cb-130">在 [ **編輯屬性**] 的 [ **關聯**] 下，選取 [檔案 **存放區**] 中的新檔案共用，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="6f6cb-131">發佈拓撲，檢查複寫狀態，然後視需要執行商務用 Skype Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="6f6cb-132">如需詳細資訊，請參閱＜[Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14))＞。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-132">For details, see [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).</span></span>

15. <span data-ttu-id="6f6cb-133">啟動命令提示字元：按一下 [ **開始**]，按一下 [ **執行**]，然後輸入 cmd.exe。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="6f6cb-134">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="6f6cb-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="6f6cb-135">/S 參數會複製到檔案、目錄及子目錄。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="6f6cb-136">/XF 參數會跳過名為 Meeting 的任何檔案。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="6f6cb-137">使用/MT 參數的目前 robocopy.exe 版本，可使用多個執行緒大幅增加複製速度。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="6f6cb-138">針對/LOG 參數使用目錄路徑和記錄檔案名，格式為 C:\Logfiles\log.txt。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="6f6cb-139">此參數會在命名位置建立作業的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="6f6cb-140">當資料複本完成時，請按一下 [Lync Server 控制台] 中的 [ **拓撲**]，然後按一下 [ **狀態**]。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="6f6cb-141">針對您停止服務的每一部伺服器或集區，選取伺服器或集區，按一下 [ **動作**]，然後按一下 [ **啟動所有服務**]。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="6f6cb-142">從拓撲中移除舊的檔案存放區，然後發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="6f6cb-143">如需詳細資訊，請參閱 [移除檔存放區](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-143">For details, see [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).</span></span>

20. <span data-ttu-id="6f6cb-144"> (選用) 登入包含您剛才移除為本機 Administrators 群組成員或 Domain Admins 群組成員的電腦，然後移除舊的檔案共用及目錄。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f6cb-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6f6cb-145">See also</span></span>

<span data-ttu-id="6f6cb-146">[將伺服器重新指派至其他檔案存放區](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="6f6cb-146">[Reassign a Server to a Different File Store](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span></span>

<span data-ttu-id="6f6cb-147">[移除檔存放區](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="6f6cb-147">[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span></span>