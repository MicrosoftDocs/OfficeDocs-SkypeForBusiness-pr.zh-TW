---
title: 'Upload通話品質儀表板中建立租使用者和 (CQD) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 瞭解如何在 CQD (中上傳租使用者和) 。
ms.openlocfilehash: 7a1f6de78e01a8988317aa99aae917aa0018e19a
ms.sourcegitcommit: 7e673b88346e07f7c777710437b19d257ccecb1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2021
ms.locfileid: "50067138"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a><span data-ttu-id="ab3b1-103">Upload通話品質儀表板中建立租使用者和 (CQD) </span><span class="sxs-lookup"><span data-stu-id="ab3b1-103">Upload tenant and building data in Call Quality Dashboard (CQD)</span></span>


<span data-ttu-id="ab3b1-104">若要在 CQD (中) 通話品質儀表板，建議您上傳租使用者和建築物資料。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-104">To get the most out of Call Quality Dashboard (CQD), we recommend that you upload your tenant and building data.</span></span> <span data-ttu-id="ab3b1-105">有 2 種類型的租使用者資料檔案，[建築物和](#upload-building-data-file)[端點](#endpoint-data-file)。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-105">There are 2 types of tenant data files, [Building](#upload-building-data-file) and [Endpoint](#endpoint-data-file).</span></span>

<span data-ttu-id="ab3b1-106">您可以在這裡下載範例租使用者資料 [範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-106">You can download a sample tenant data template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).</span></span> <span data-ttu-id="ab3b1-107">若要瞭解建立地圖的協助，請參閱建立 [CQD 的建築物地圖](CQD-building-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-107">For help with building mapping, read [Create a building map for CQD](CQD-building-mapping.md).</span></span>

<span data-ttu-id="ab3b1-108">從 CQD 摘要報表儀表板中，選取 CQD Upload 功能表中的設定 租使用者資料 (CQD 功能表頂端的齒輪圖示) 。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-108">From the CQD Summary Reports dashboard, select **Tenant Data Upload** from the CQD **Settings** menu (a gear icon at the top of CQD).</span></span> <span data-ttu-id="ab3b1-109">管理員可以從這裡上傳其組織的建築物和端點資訊，例如 IP 位址和地理資訊的映射、每個無線存取點及其 MAC 位址的映射等。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-109">From here, admins can upload their organization's building and endpoint information, such as mapping of IP addresses and geographical information, mapping each wireless access point and its MAC address, etc.</span></span>

1. <span data-ttu-id="ab3b1-110">從 (Teams 系統管理中心或) 開啟 CQD 圖示，然後選取右上角的齒輪圖示，然後從摘要報表頁面選擇 Upload 租使用者資料。 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)  </span><span class="sxs-lookup"><span data-stu-id="ab3b1-110">Open CQD (from the Teams admin center, or at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), then select the gear icon in the upper-right corner and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

   ![上傳資料時出現的對話方塊螢幕擷取畫面](media/qerguide-image-tenantdataupload.png)
    
2. <span data-ttu-id="ab3b1-112">或者，如果這是您第一次流覽 CQD，系統將會要求您上傳建築物資料。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-112">Alternatively, if this is your first time visiting CQD, you'll be asked to upload building data.</span></span> <span data-ttu-id="ab3b1-113">您可以選取 Upload **立即** 流覽至租使用者 **資料Upload** 頁面。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-113">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

   ![通知使用者上傳建築物資料的橫幅螢幕擷取畫面](media/qerguide-image-buildingdatauploadbanner.png)

3. <span data-ttu-id="ab3b1-115">在租 **使用者資料Upload** 頁面上，選取 **流覽** 以選擇資料檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-115">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

4. <span data-ttu-id="ab3b1-116">選取資料檔案之後，請指定 **開始日期** ，也可以指定結束日期。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-116">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

5. <span data-ttu-id="ab3b1-117">選取開始日期 **之後**，選取 **Upload** 檔案上傳到 CQD。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-117">After selecting **Start date**, select **Upload** to upload the file to CQD.</span></span> <br><br><span data-ttu-id="ab3b1-118">在上傳檔案之前，檔案會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-118">Before the file is uploaded, it's validated.</span></span> <span data-ttu-id="ab3b1-119">如果驗證失敗，會顯示錯誤訊息，要求您更正檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-119">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="ab3b1-120">下圖顯示資料檔案中的欄數不正確時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-120">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

   ![顯示建築物資料上傳錯誤的對話方塊範例](media/qerguide-image-buildingdatauploaderror.png)
 
6. <span data-ttu-id="ab3b1-122">如果在驗證期間未發生錯誤，檔案上傳將會成功。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-122">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="ab3b1-123">接著，您可以在我的上傳資料表中看到上傳的資料檔案，顯示該頁面底部目前租使用者所有上傳檔案的完整清單。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-123">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="ab3b1-124">最多可能需要四小時才能完成建築物檔案的處理。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-124">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="ab3b1-125">如果您已經上傳建築物檔案，而且需要新增可能錯過或排除的子網，請新增新的子網來修改原始檔案、移除目前的檔案，然後重新上傳新編輯的檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-125">If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="ab3b1-126">CQD 中只能有一個使用中的建築物資料檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-126">There can be only one active building data file in CQD.</span></span> 


## <a name="upload-building-data-file"></a><span data-ttu-id="ab3b1-127">Upload建資料檔案</span><span class="sxs-lookup"><span data-stu-id="ab3b1-127">Upload building data file</span></span>

<span data-ttu-id="ab3b1-128">CQD 中第一種類型的租使用者資料檔案 **是建築物資料檔案** 。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-128">The first type of tenant data file in CQD is the **Building** data file.</span></span> <span data-ttu-id="ab3b1-129">子網資料行是展開 Network+NetworkRange 資料行，然後將子網資料行加入通話記錄的第一個子網或第二個子網資料行，以顯示建築物、城市、國家/地區或地區資訊。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-129">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="ab3b1-130">您上傳的資料檔案格式必須符合下列準則，才能在上傳前通過驗證檢查：</span><span class="sxs-lookup"><span data-stu-id="ab3b1-130">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="ab3b1-131">檔案必須是 .tsv 檔案， (欄必須以 TAB) 分隔.csv或 (欄以逗號分隔) 。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-131">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="ab3b1-132">資料檔案不包含表格標題列。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-132">The data file doesn't include a table header row.</span></span> <span data-ttu-id="ab3b1-133">資料檔案的第一行應該是實際資料，而不是標題標籤 ，例如「網路」。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-133">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>

- <span data-ttu-id="ab3b1-134">檔案中的資料類型只能是 String、Integer 或布林值。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-134">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="ab3b1-135">對於整數資料類型，值必須是數值。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-135">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="ab3b1-136">布林值必須是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-136">Boolean values must be either 0 or 1.</span></span>

- <span data-ttu-id="ab3b1-137">如果欄使用 String 資料類型，則資料欄位可以是空白的，但仍必須以索引鍵或逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-137">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="ab3b1-138">空白資料欄位只指派空的 String 值。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-138">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="ab3b1-139">每個租使用者資料檔案有 1，000，000 個展開列數限制。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-139">There is a 1,000,000 expanded row limit per tenant data file.</span></span>

- <span data-ttu-id="ab3b1-140">每一列必須有 15 個欄，每一欄都必須有適當的資料類型，而且欄的順序必須按照下表 (逗號或定位字元分隔) ：</span><span class="sxs-lookup"><span data-stu-id="ab3b1-140">There must be 15 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):</span></span>

  <span data-ttu-id="ab3b1-141">**建立資料檔案格式**</span><span class="sxs-lookup"><span data-stu-id="ab3b1-141">**Building data file format**</span></span>
  
  | <span data-ttu-id="ab3b1-142">欄名稱</span><span class="sxs-lookup"><span data-stu-id="ab3b1-142">Column name</span></span>        | <span data-ttu-id="ab3b1-143">資料類型</span><span class="sxs-lookup"><span data-stu-id="ab3b1-143">Data type</span></span> | <span data-ttu-id="ab3b1-144">範例</span><span class="sxs-lookup"><span data-stu-id="ab3b1-144">Example</span></span>                   | <span data-ttu-id="ab3b1-145">指導方針</span><span class="sxs-lookup"><span data-stu-id="ab3b1-145">Guidance</span></span>              |
  |--------------------|-----------|---------------------------|-----------------------|
  | <span data-ttu-id="ab3b1-146">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="ab3b1-146">NetworkIP</span></span>          | <span data-ttu-id="ab3b1-147">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-147">String</span></span>    | <span data-ttu-id="ab3b1-148">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="ab3b1-148">192.168.1.0</span></span>               | <span data-ttu-id="ab3b1-149">必要</span><span class="sxs-lookup"><span data-stu-id="ab3b1-149">Required</span></span>              |
  | <span data-ttu-id="ab3b1-150">NetworkName</span><span class="sxs-lookup"><span data-stu-id="ab3b1-150">NetworkName</span></span>        | <span data-ttu-id="ab3b1-151">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-151">String</span></span>    | <span data-ttu-id="ab3b1-152">USA/Seattle/SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="ab3b1-152">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="ab3b1-153">需要<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ab3b1-153">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="ab3b1-154">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="ab3b1-154">NetworkRange</span></span>       | <span data-ttu-id="ab3b1-155">數量</span><span class="sxs-lookup"><span data-stu-id="ab3b1-155">Number</span></span>    | <span data-ttu-id="ab3b1-156">26</span><span class="sxs-lookup"><span data-stu-id="ab3b1-156">26</span></span>                        | <span data-ttu-id="ab3b1-157">必要</span><span class="sxs-lookup"><span data-stu-id="ab3b1-157">Required</span></span>              |
  | <span data-ttu-id="ab3b1-158">BuildingName</span><span class="sxs-lookup"><span data-stu-id="ab3b1-158">BuildingName</span></span>       | <span data-ttu-id="ab3b1-159">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-159">String</span></span>    | <span data-ttu-id="ab3b1-160">西雅圖-SEA-1</span><span class="sxs-lookup"><span data-stu-id="ab3b1-160">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="ab3b1-161">需要<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ab3b1-161">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="ab3b1-162">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="ab3b1-162">OwnershipType</span></span>      | <span data-ttu-id="ab3b1-163">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-163">String</span></span>    | <span data-ttu-id="ab3b1-164">Contoso</span><span class="sxs-lookup"><span data-stu-id="ab3b1-164">Contoso</span></span>                   | <span data-ttu-id="ab3b1-165">選用</span><span class="sxs-lookup"><span data-stu-id="ab3b1-165">Optional</span></span>              |
  | <span data-ttu-id="ab3b1-166">BuildingType</span><span class="sxs-lookup"><span data-stu-id="ab3b1-166">BuildingType</span></span>       | <span data-ttu-id="ab3b1-167">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-167">String</span></span>    | <span data-ttu-id="ab3b1-168">IT 終止</span><span class="sxs-lookup"><span data-stu-id="ab3b1-168">IT Termination</span></span>            | <span data-ttu-id="ab3b1-169">選用</span><span class="sxs-lookup"><span data-stu-id="ab3b1-169">Optional</span></span>              |
  | <span data-ttu-id="ab3b1-170">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="ab3b1-170">BuildingOfficeType</span></span> | <span data-ttu-id="ab3b1-171">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-171">String</span></span>    | <span data-ttu-id="ab3b1-172">工程</span><span class="sxs-lookup"><span data-stu-id="ab3b1-172">Engineering</span></span>               | <span data-ttu-id="ab3b1-173">選用</span><span class="sxs-lookup"><span data-stu-id="ab3b1-173">Optional</span></span>              |
  | <span data-ttu-id="ab3b1-174">城市</span><span class="sxs-lookup"><span data-stu-id="ab3b1-174">City</span></span>               | <span data-ttu-id="ab3b1-175">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-175">String</span></span>    | <span data-ttu-id="ab3b1-176">西雅圖</span><span class="sxs-lookup"><span data-stu-id="ab3b1-176">Seattle</span></span>                   | <span data-ttu-id="ab3b1-177">推薦</span><span class="sxs-lookup"><span data-stu-id="ab3b1-177">Recommended</span></span>           |
  | <span data-ttu-id="ab3b1-178">郵遞區號</span><span class="sxs-lookup"><span data-stu-id="ab3b1-178">ZipCode</span></span>            | <span data-ttu-id="ab3b1-179">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-179">String</span></span>    | <span data-ttu-id="ab3b1-180">98001</span><span class="sxs-lookup"><span data-stu-id="ab3b1-180">98001</span></span>                     | <span data-ttu-id="ab3b1-181">推薦</span><span class="sxs-lookup"><span data-stu-id="ab3b1-181">Recommended</span></span>           |
  | <span data-ttu-id="ab3b1-182">國家</span><span class="sxs-lookup"><span data-stu-id="ab3b1-182">Country</span></span>            | <span data-ttu-id="ab3b1-183">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-183">String</span></span>    | <span data-ttu-id="ab3b1-184">我們</span><span class="sxs-lookup"><span data-stu-id="ab3b1-184">US</span></span>                        | <span data-ttu-id="ab3b1-185">推薦</span><span class="sxs-lookup"><span data-stu-id="ab3b1-185">Recommended</span></span>           |
  | <span data-ttu-id="ab3b1-186">狀態</span><span class="sxs-lookup"><span data-stu-id="ab3b1-186">State</span></span>              | <span data-ttu-id="ab3b1-187">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-187">String</span></span>    | <span data-ttu-id="ab3b1-188">窪</span><span class="sxs-lookup"><span data-stu-id="ab3b1-188">WA</span></span>                        | <span data-ttu-id="ab3b1-189">推薦</span><span class="sxs-lookup"><span data-stu-id="ab3b1-189">Recommended</span></span>           |
  | <span data-ttu-id="ab3b1-190">地區</span><span class="sxs-lookup"><span data-stu-id="ab3b1-190">Region</span></span>             | <span data-ttu-id="ab3b1-191">String</span><span class="sxs-lookup"><span data-stu-id="ab3b1-191">String</span></span>    | <span data-ttu-id="ab3b1-192">MSUS</span><span class="sxs-lookup"><span data-stu-id="ab3b1-192">MSUS</span></span>                      | <span data-ttu-id="ab3b1-193">推薦</span><span class="sxs-lookup"><span data-stu-id="ab3b1-193">Recommended</span></span>           |
  | <span data-ttu-id="ab3b1-194">InsideCorp<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ab3b1-194">InsideCorp<sup>2</sup></span></span>         | <span data-ttu-id="ab3b1-195">Bool</span><span class="sxs-lookup"><span data-stu-id="ab3b1-195">Bool</span></span>      | <span data-ttu-id="ab3b1-196">1</span><span class="sxs-lookup"><span data-stu-id="ab3b1-196">1</span></span>             | <span data-ttu-id="ab3b1-197">必要</span><span class="sxs-lookup"><span data-stu-id="ab3b1-197">Required</span></span>              |
  | <span data-ttu-id="ab3b1-198">ExpressRoute<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ab3b1-198">ExpressRoute<sup>3</sup></span></span>       | <span data-ttu-id="ab3b1-199">Bool</span><span class="sxs-lookup"><span data-stu-id="ab3b1-199">Bool</span></span>      | <span data-ttu-id="ab3b1-200">0</span><span class="sxs-lookup"><span data-stu-id="ab3b1-200">0</span></span>             | <span data-ttu-id="ab3b1-201">必要</span><span class="sxs-lookup"><span data-stu-id="ab3b1-201">Required</span></span>              |
  | <span data-ttu-id="ab3b1-202">Vpn</span><span class="sxs-lookup"><span data-stu-id="ab3b1-202">VPN</span></span>                | <span data-ttu-id="ab3b1-203">Bool</span><span class="sxs-lookup"><span data-stu-id="ab3b1-203">Bool</span></span>      | <span data-ttu-id="ab3b1-204">0</span><span class="sxs-lookup"><span data-stu-id="ab3b1-204">0</span></span>                         | <span data-ttu-id="ab3b1-205">選用</span><span class="sxs-lookup"><span data-stu-id="ab3b1-205">Optional</span></span>              |

  <span data-ttu-id="ab3b1-206"><sup>1</sup> 雖然 CQD 不需要，但範本已配置為顯示建築物和網路名稱。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-206"><sup>1</sup> While not required by CQD, the templates are configured to display Building and Network name.</span></span>

  <span data-ttu-id="ab3b1-207"><sup>2</sup> 此設定可用來反映子網是否位於公司網路內。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-207"><sup>2</sup> This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="ab3b1-208">您可以自訂其他用途的使用量。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-208">You can customize usage for other purposes.</span></span>

  <span data-ttu-id="ab3b1-209"><sup>3</sup> 此設定可用來反映網路是否使用 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-209"><sup>3</sup> This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="ab3b1-210">您可以自訂其他用途的使用量。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-210">You can customize usage for other purposes.</span></span>  

  <span data-ttu-id="ab3b1-211">**範例列：**</span><span class="sxs-lookup"><span data-stu-id="ab3b1-211">**Sample row:**</span></span>

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="ab3b1-212">網路範圍可用來代表一個超網路， (多個子網的組合，以及單一路由首碼) 。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-212">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="ab3b1-213">所有新建築物上傳都會檢查任何重迭範圍。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-213">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="ab3b1-214">如果您先前上傳過建置檔案，您應該先下載目前的檔案，然後重新上傳檔案，找出任何重迭之處並修正問題，然後再重新上傳。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-214">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="ab3b1-215">先前上傳檔案的任何重迭都可能會導致子網與報告中建築物的相互比對錯誤。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-215">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="ab3b1-216">某些 VPN 的實現無法正確報告子網資訊。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-216">Certain VPN implementations do not accurately report the subnet information.</span></span> 
>
> <span data-ttu-id="ab3b1-217">VPN 欄為選擇性，預設為 0。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-217">The VPN column is optional and will default to 0.</span></span> <span data-ttu-id="ab3b1-218">如果 VPN 欄的值設為 1，該列所代表的子網將會完全展開，以符合子網內的所有 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-218">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span> <span data-ttu-id="ab3b1-219">請謹慎且僅適用于 VPN 子網，因為完全展開這些子網會對建立資料之查詢的查詢時間造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-219">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span> <span data-ttu-id="ab3b1-220">如果子網的擴充導致超過 1，000，000 的擴充列限制，系統將不會接受建房檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-220">If the expansion of the subnet results in the expansion row limit of 1,000,000 being exceeded, the building file will not be accepted.</span></span>


### <a name="supernetting"></a><span data-ttu-id="ab3b1-221">超網路</span><span class="sxs-lookup"><span data-stu-id="ab3b1-221">Supernetting</span></span>

<span data-ttu-id="ab3b1-222">您可以使用超網路，通常稱為無Inter-Domain路由 (CIDR，) 定義每個子網。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-222">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="ab3b1-223">超 *網路* 是多個共用單一路由首碼的子網組合。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-223">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="ab3b1-224">您可以不使用每個子網新增專案，而是使用超網路位址。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-224">Instead of adding an entry for each subnet, you can use the supernetted address.</span></span> <span data-ttu-id="ab3b1-225">支援超網路，但我們不建議使用它。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-225">Supernetting is supported, but we don't recommend using it.</span></span>

<span data-ttu-id="ab3b1-226">例如，Contoso 的行銷大樓是由下列子網所建立：</span><span class="sxs-lookup"><span data-stu-id="ab3b1-226">For example, Contoso's marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="ab3b1-227">10.1.0.0/24 -一樓</span><span class="sxs-lookup"><span data-stu-id="ab3b1-227">10.1.0.0/24—first floor</span></span>
-   <span data-ttu-id="ab3b1-228">10.1.1.0/24-二樓</span><span class="sxs-lookup"><span data-stu-id="ab3b1-228">10.1.1.0/24—second floor</span></span>
-   <span data-ttu-id="ab3b1-229">10.1.2.0/24 -三樓</span><span class="sxs-lookup"><span data-stu-id="ab3b1-229">10.1.2.0/24—third floor</span></span>
-   <span data-ttu-id="ab3b1-230">10.1.3.0/24 -四樓</span><span class="sxs-lookup"><span data-stu-id="ab3b1-230">10.1.3.0/24—fourth floor</span></span>

<span data-ttu-id="ab3b1-231">您可以不使用每個子網新增專案，而是使用超網路位址 ，在此範例中為 10.1.0.0/22。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-231">Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="ab3b1-232">Network = 10.1.0.0</span><span class="sxs-lookup"><span data-stu-id="ab3b1-232">Network = 10.1.0.0</span></span>
-   <span data-ttu-id="ab3b1-233">網路範圍 = 22</span><span class="sxs-lookup"><span data-stu-id="ab3b1-233">Network Range = 22</span></span>

<span data-ttu-id="ab3b1-234">以下是在實行超網路之前，請考慮的一些專案：</span><span class="sxs-lookup"><span data-stu-id="ab3b1-234">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="ab3b1-235">超網路只能用於具有 8 位到 28 位元遮罩的子網映射。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-235">Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="ab3b1-236">超網路佔用較少的前置時間，但代價是降低資料的豐富性。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-236">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="ab3b1-237">假設子網 10.1.2.0 發生品質問題。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-237">Let's say there's a quality problem involving subnet 10.1.2.0.</span></span> <span data-ttu-id="ab3b1-238">如果您實行超網路化，您不會知道子網在建築物中的位置，或網路類型 (例如實驗室) 。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-238">If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="ab3b1-239">如果您已經定義建築物的所有子網和上傳的樓面位置資訊，就能看到這一區別。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-239">If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.</span></span>

-   <span data-ttu-id="ab3b1-240">請確保超網路位址正確無誤，而且不會捕獲不想要的子網。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-240">It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.</span></span>

-   <span data-ttu-id="ab3b1-241">在資料中尋找 192.168.0.0 是相當常見的。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-241">It's quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="ab3b1-242">對於許多組織來說，這表示使用者在家中。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-242">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="ab3b1-243">對其他人來說，這是衛星辦公室的 IP 位址方案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-243">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="ab3b1-244">如果貴組織有使用此配置的辦公室，請勿將其納入您的建房檔案中，因為使用常見的子網難以區分家用和內部 [網路](quality-of-experience-review-guide.md#common-subnets)。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-244">If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide.md#common-subnets).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ab3b1-245">網路範圍可用來代表超網路。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-245">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="ab3b1-246">所有新的建築物資料檔案上傳都會檢查是否有重迭的範圍。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-246">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="ab3b1-247">如果您先前上傳過建置檔案，您應該下載目前的檔案並再次上傳，以找出任何重迭之處並修正問題。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-247">If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="ab3b1-248">先前上傳檔案的任何重迭都可能會導致子網與報告中建築物的相互映射錯誤。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-248">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span>

### <a name="vpn"></a><span data-ttu-id="ab3b1-249">Vpn</span><span class="sxs-lookup"><span data-stu-id="ab3b1-249">VPN</span></span>

<span data-ttu-id="ab3b1-250">QoE (qoE) 用戶端傳送至 Microsoft 365 或 Office 365 的資料 -這是 CQD 資料的來源地 -包含 VPN 標號。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-250">The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="ab3b1-251">CQD 會視此為第一個 VPN 和第二個 VPN 維度。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-251">CQD will see this as the First VPN and Second VPN dimensions.</span></span> <span data-ttu-id="ab3b1-252">不過，此標號仰賴 VPN 廠商向 Windows註冊的 VPN 網路介面卡是遠端存取介面卡的報告。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-252">However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="ab3b1-253">並非所有 VPN 廠商都正確註冊遠端存取介面卡。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-253">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="ab3b1-254">因此，您可能無法使用內建的 VPN 查詢篩選。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-254">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="ab3b1-255">使用上述的 VPN 資料行來正確標記和識別 VPN 子網。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-255">Use the VPN column discussed above to accurately mark and identify VPN subnets.</span></span> <span data-ttu-id="ab3b1-256">此外，為 VPN 網路貼上標籤也是很好的做法，方便您識別報表。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-256">It is also good practice to label your VPN networks for easy identification in your reports.</span></span> <span data-ttu-id="ab3b1-257">以下是如何標示 VPN 子網的兩個範例：</span><span class="sxs-lookup"><span data-stu-id="ab3b1-257">Below are two examples of how to label your VPN subnets:</span></span>

- <span data-ttu-id="ab3b1-258">在 **VPN 子網的** 此欄位中輸入 「VPN」以定義網路名稱。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-258">Define a **Network Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![顯示使用網路名稱的 VPN 的 QCD 報表螢幕擷取畫面](media/qerguide-image-vpnnetworkname.png)

- <span data-ttu-id="ab3b1-260">在 VPN **子網的** 此欄位中輸入 「VPN」，以定義建築物名稱。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-260">Define a **Building Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![顯示使用建築物名稱的 VPN 的 QCD 報表螢幕擷取畫面](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> <span data-ttu-id="ab3b1-262">已知 VPN 連接在基礎連接為無線時，會誤認為網路連接類型為有線。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-262">VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless.</span></span> <span data-ttu-id="ab3b1-263">當您在 VPN 連接上查看品質時，無法假設已正確識別連線類型。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-263">When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.</span></span>

## <a name="endpoint-data-file"></a><span data-ttu-id="ab3b1-264">端點資料檔案</span><span class="sxs-lookup"><span data-stu-id="ab3b1-264">Endpoint data file</span></span>

<span data-ttu-id="ab3b1-265">另一種類型的 CQD 租使用者資料檔案是 **端點** 資料檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-265">The other type of CQD tenant data file is the **Endpoint** data file.</span></span> <span data-ttu-id="ab3b1-266">資料行值會用於通話記錄的第一個用戶端端點名稱或第二個用戶端端點名稱欄，以顯示端點建立、模型或類型資訊。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-266">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="ab3b1-267">您上傳的資料檔案格式必須符合下列準則，才能在上傳前通過驗證檢查：</span><span class="sxs-lookup"><span data-stu-id="ab3b1-267">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="ab3b1-268">檔案必須是 .tsv 檔案， (欄必須以 TAB) 分隔.csv或 (欄以逗號分隔) 。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-268">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="ab3b1-269">資料檔案的內容不包含表格標題。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-269">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="ab3b1-270">資料檔案的第一行應該是實際資料，而不是標題標籤 ，例如「端點名稱」。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-270">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>

- <span data-ttu-id="ab3b1-271">所有七欄都只會使用 String 資料類型。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-271">All seven columns use the String data type only.</span></span> <span data-ttu-id="ab3b1-272">允許的長度上限為 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-272">The maximum allowed length is 64 characters.</span></span>

- <span data-ttu-id="ab3b1-273">資料欄位可以是空白的，但仍必須以定位字元或逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-273">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="ab3b1-274">空白資料欄位只指派空的 String 值。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-274">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="ab3b1-275">端點名稱必須是唯一的，否則上傳失敗。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-275">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="ab3b1-276">如果有重複的列或兩列使用相同的端點名稱，衝突將導致不正確的聯入。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-276">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>

- <span data-ttu-id="ab3b1-277">EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自訂的標籤。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-277">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="ab3b1-278">它們可以是空白的字串或值，例如「IT 部門指定的 2018 膝上型電腦」或「資產標記 5678」。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-278">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>

- <span data-ttu-id="ab3b1-279">每一列必須有七欄，而且欄的順序必須如下：</span><span class="sxs-lookup"><span data-stu-id="ab3b1-279">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="ab3b1-280">**域順序：**</span><span class="sxs-lookup"><span data-stu-id="ab3b1-280">**Field order:**</span></span>

  <span data-ttu-id="ab3b1-281">端點名稱、端點模型、端點模型、端點類型、端點標籤1、端點標籤2、端點標籤3</span><span class="sxs-lookup"><span data-stu-id="ab3b1-281">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="ab3b1-282">**範例列：**</span><span class="sxs-lookup"><span data-stu-id="ab3b1-282">**Sample row:**</span></span>

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a><span data-ttu-id="ab3b1-283">更新建築物檔案</span><span class="sxs-lookup"><span data-stu-id="ab3b1-283">Update a building file</span></span>

<span data-ttu-id="ab3b1-284">在收集建築物和子網資訊時，系統管理員通常會在一段時間的多次反覆運算中上傳建築物檔案，並新增新的子網及其建築物資訊。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-284">While gathering building and subnet information, administrators will often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available.</span></span> <span data-ttu-id="ab3b1-285">發生這種情況時，您必須重新上傳建築物檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-285">When this occurs, you'll need to re-upload your building file.</span></span> <span data-ttu-id="ab3b1-286">此程式與上一節所述的初始上傳類似，但下列一節所述的一些例外情況除外。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-286">This process is like the initial upload as described in the previous section, with a few exceptions as noted in the following section.</span></span>

> [!Important]
> <span data-ttu-id="ab3b1-287">一次只能使用一個建築物檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-287">Only one building file can be active at a time.</span></span> <span data-ttu-id="ab3b1-288">多個建築物檔案不會累加。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-288">Multiple building files aren't cumulative.</span></span>

## <a name="add-net-new-subnets"></a><span data-ttu-id="ab3b1-289">新增淨新子網</span><span class="sxs-lookup"><span data-stu-id="ab3b1-289">Add net new subnets</span></span>

<span data-ttu-id="ab3b1-290">有時候，您需要在 CQD 中新增網路新子網，這些子網原本不是網路拓撲的一部分。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-290">There are times when you'll need to add net new subnets to CQD that weren't originally part of your network topology.</span></span> <span data-ttu-id="ab3b1-291">若要新增淨新子網，請從 CQD 的租使用者資料 **Upload頁面執行** 下列操作：</span><span class="sxs-lookup"><span data-stu-id="ab3b1-291">To add net new subnets, do the following from the **Tenant Data Upload** page in CQD:</span></span>

1.  <span data-ttu-id="ab3b1-292">如果您還沒有最新版本的檔案，請下載原始檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-292">Download the original file, if you don't already have an up-to-date copy.</span></span>

1.  <span data-ttu-id="ab3b1-293">移除 CQD 中的目前檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-293">Remove the current file in CQD.</span></span>

1.  <span data-ttu-id="ab3b1-294">編輯原始建築物檔案，並提供在取得新子網之前至少一天的結束日期。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-294">Edit the original building file and provide an end date that occurs at least one day before the net new subnets were acquired.</span></span>

1.  <span data-ttu-id="ab3b1-295">將淨新子網附加到原始建築物檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-295">Append the net new subnets to the original building file.</span></span>

1.  <span data-ttu-id="ab3b1-296">Upload新修改的建築物檔案，並設定前一個建築物檔案結束後一天的開始日期。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-296">Upload the newly modified building file, and set the start date for one day after the previous building file ends.</span></span>

## <a name="add-missing-subnets"></a><span data-ttu-id="ab3b1-297">新增遺失的子網</span><span class="sxs-lookup"><span data-stu-id="ab3b1-297">Add missing subnets</span></span>

<span data-ttu-id="ab3b1-298">上傳受管理網路的建築物資訊之後，每個受管理網路都應該有建築物關聯。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-298">After you upload building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="ab3b1-299">不過，情況不一定一定如此;通常會漏接幾個子網。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-299">However, this won't always be the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="ab3b1-300">若要尋找這些遺失的網路，請檢閱 CQD 中體驗品質 **報告頁面上的** 遺失子網報告。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-300">To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD.</span></span> <span data-ttu-id="ab3b1-301">這會以 10 或更多音訊資料流程呈現所有子網，這些音訊流未在建房資料檔案中定義，且標示為外部。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-301">This presents all the subnets with 10 or more audio streams that aren't defined in the building data file and are being marked as outside.</span></span> <span data-ttu-id="ab3b1-302">請在此清單中確保沒有受管理網路。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-302">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="ab3b1-303">如果子網遺失，請使用下列程式更新原始建築物資料檔案，然後重新上傳至 CQD。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-303">If subnets are missing, use the following procedure to update the original building data file and re-upload it to CQD.</span></span>

1. <span data-ttu-id="ab3b1-304">前往 CQD **Upload** 租使用者資料頁面。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-304">Go to the **Tenant Data Upload** page in CQD.</span></span>

1. <span data-ttu-id="ab3b1-305">如果您還沒有最新版本的檔案，請下載原始檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-305">Download the original file, if you don't already have an up-to-date copy.</span></span>

1. <span data-ttu-id="ab3b1-306">移除 CQD 中的目前檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-306">Remove the current file in CQD.</span></span>

1. <span data-ttu-id="ab3b1-307">將新的子網附加到原始檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-307">Append the new subnets to the original file.</span></span>

1. <span data-ttu-id="ab3b1-308">Upload建立檔案。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-308">Upload the building file.</span></span> <span data-ttu-id="ab3b1-309">請務必將開始日期設定為至少八個月之前，讓 CQD 處理歷史資料。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-309">Be sure to set the start date to at least eight months prior so that CQD will process historical data.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="ab3b1-310">您必須將租使用者識別碼新增為第二個租使用者識別碼的查詢篩選，才能篩選報表，只查看貴組織的租使用者資料。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-310">You'll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization's tenant data.</span></span> <span data-ttu-id="ab3b1-311">否則，報表會顯示聯盟子網。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-311">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="ab3b1-312">請務必將月年報表篩選調整為目前月份。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-312">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="ab3b1-313">選取 **編輯**，然後調整月 **年** 報表篩選以儲存新的預設月份。</span><span class="sxs-lookup"><span data-stu-id="ab3b1-313">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ab3b1-314">相關主題</span><span class="sxs-lookup"><span data-stu-id="ab3b1-314">Related topics</span></span>

[<span data-ttu-id="ab3b1-315">建立 CQD 的建築物地圖</span><span class="sxs-lookup"><span data-stu-id="ab3b1-315">Create a building map for CQD</span></span>](CQD-building-mapping.md)

[<span data-ttu-id="ab3b1-316">改善及監控通話品質Teams</span><span class="sxs-lookup"><span data-stu-id="ab3b1-316">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="ab3b1-317">什麼是 CQD？</span><span class="sxs-lookup"><span data-stu-id="ab3b1-317">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="ab3b1-318">設定通話品質儀表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="ab3b1-318">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="ab3b1-319">CQD 資料和報表</span><span class="sxs-lookup"><span data-stu-id="ab3b1-319">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="ab3b1-320">使用 CQD 管理通話和會議品質</span><span class="sxs-lookup"><span data-stu-id="ab3b1-320">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="ab3b1-321">CQD 中可用的維度和度量</span><span class="sxs-lookup"><span data-stu-id="ab3b1-321">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="ab3b1-322">CQD 中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="ab3b1-322">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="ab3b1-323">使用 Power BI分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="ab3b1-323">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
