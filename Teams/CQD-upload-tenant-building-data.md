---
title: '在通話品質儀表板中上傳租使用者並建立資料 (CQD) '
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
description: 瞭解如何在通話品質儀表板 (CQD) 中上傳租使用者和組建資料。
ms.openlocfilehash: 1ee722e63a8699e1447ffc0c2bc859a6a080d220
ms.sourcegitcommit: bac9aa29074ef32387dc05b3918e87d4c38d195d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2020
ms.locfileid: "49385630"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a><span data-ttu-id="c92cc-103">在通話品質儀表板中上傳租使用者並建立資料 (CQD) </span><span class="sxs-lookup"><span data-stu-id="c92cc-103">Upload tenant and building data in Call Quality Dashboard (CQD)</span></span>


<span data-ttu-id="c92cc-104">若要充分利用通話品質儀表板 (CQD) ，建議您上傳租使用者並建立資料。</span><span class="sxs-lookup"><span data-stu-id="c92cc-104">To get the most out of Call Quality Dashboard (CQD), we recommend that you upload your tenant and building data.</span></span> <span data-ttu-id="c92cc-105">有2種類型的租使用者資料檔，即 [建立](#upload-building-data-file) 與 [端點](#endpoint-data-file)。</span><span class="sxs-lookup"><span data-stu-id="c92cc-105">There are 2 types of tenant data files, [Building](#upload-building-data-file) and [Endpoint](#endpoint-data-file).</span></span>

<span data-ttu-id="c92cc-106">您可以 [在這裡](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下載範例租使用者資料範本。</span><span class="sxs-lookup"><span data-stu-id="c92cc-106">You can download a sample tenant data template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).</span></span> <span data-ttu-id="c92cc-107">如需有關建立對應的說明，請參閱 [建立 CQD 的組建地圖](CQD-building-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="c92cc-107">For help with building mapping, read [Create a building map for CQD](CQD-building-mapping.md).</span></span>

<span data-ttu-id="c92cc-108">從 [CQD 摘要報告] 儀表板中，從 [CQD **設定**] 功能表中選取 **[租使用者資料上傳**]， (位於 [CQD]) 頂端的齒輪圖示。</span><span class="sxs-lookup"><span data-stu-id="c92cc-108">From the CQD Summary Reports dashboard, select **Tenant Data Upload** from the CQD **Settings** menu (a gear icon at the top of CQD).</span></span> <span data-ttu-id="c92cc-109">在此，系統管理員可以上傳其組織的建築物和端點資訊，例如 IP 位址和地理資訊的對應、對應每個無線存取點及其 MAC 位址等。</span><span class="sxs-lookup"><span data-stu-id="c92cc-109">From here, admins can upload their organization's building and endpoint information, such as mapping of IP addresses and geographical information, mapping each wireless access point and its MAC address, etc.</span></span>

1. <span data-ttu-id="c92cc-110">從 [團隊系統管理中心] 開啟 [CQD (]，或在 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)) ，選取右上角的齒輪圖示，然後從 [**摘要報告**] 頁面選擇 [**租使用者資料上傳**]。</span><span class="sxs-lookup"><span data-stu-id="c92cc-110">Open CQD (from the Teams admin center, or at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), then select the gear icon in the upper-right corner and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

   ![上傳資料時出現之對話方塊的螢幕擷取畫面](media/qerguide-image-tenantdataupload.png)
    
2. <span data-ttu-id="c92cc-112">或者，如果這是您第一次造訪 CQD，系統會要求您上傳 [組建資料]。</span><span class="sxs-lookup"><span data-stu-id="c92cc-112">Alternatively, if this is your first time visiting CQD, you'll be asked to upload building data.</span></span> <span data-ttu-id="c92cc-113">您可以選取 **[立即上傳** ]，快速流覽至 [ **租使用者資料上傳** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c92cc-113">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

   ![通知使用者上傳建立資料的橫幅螢幕擷取畫面](media/qerguide-image-buildingdatauploadbanner.png)

3. <span data-ttu-id="c92cc-115">在 [ **租使用者資料上傳** ] 頁面上，選取 **[流覽]** 來選擇資料檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-115">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

4. <span data-ttu-id="c92cc-116">選取資料檔之後，請指定 **開始日期** ，也可以指定結束日期。</span><span class="sxs-lookup"><span data-stu-id="c92cc-116">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

5. <span data-ttu-id="c92cc-117">選取 [ **開始日期**] 後，選取 **[上傳** ]，將檔案上傳到 CQD。</span><span class="sxs-lookup"><span data-stu-id="c92cc-117">After selecting **Start date**, select **Upload** to upload the file to CQD.</span></span> <br><br><span data-ttu-id="c92cc-118">檔案上傳之前，會進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c92cc-118">Before the file is uploaded, it's validated.</span></span> <span data-ttu-id="c92cc-119">如果驗證失敗，則會顯示一則錯誤訊息，要求您更正檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-119">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="c92cc-120">下圖顯示當資料檔案中的欄數不正確時所發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="c92cc-120">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

   ![顯示組建資料上傳錯誤的對話方塊範例](media/qerguide-image-buildingdatauploaderror.png)
 
6. <span data-ttu-id="c92cc-122">如果驗證期間沒有發生任何錯誤，檔案上傳就會成功。</span><span class="sxs-lookup"><span data-stu-id="c92cc-122">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="c92cc-123">接著，您可以在 [我的上 **傳** ] 資料表中看到上傳的資料檔，該檔案會在該頁面的底部顯示目前租使用者的所有已上傳檔案的完整清單。</span><span class="sxs-lookup"><span data-stu-id="c92cc-123">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="c92cc-124">可能需要長達四個小時的時間，才能完成建立檔的處理。</span><span class="sxs-lookup"><span data-stu-id="c92cc-124">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="c92cc-125">如果您已上傳檔案，且需要新增可能已錯過或排除的子網，請修改原始檔案，方法是新增子網、移除目前的檔案，然後重新上傳新編輯的檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-125">If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="c92cc-126">在 CQD 中，只能有一個作用中的組建資料檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-126">There can be only one active building data file in CQD.</span></span> 


## <a name="upload-building-data-file"></a><span data-ttu-id="c92cc-127">上傳資料檔案</span><span class="sxs-lookup"><span data-stu-id="c92cc-127">Upload building data file</span></span>

<span data-ttu-id="c92cc-128">CQD 中的第一個租使用者資料檔類型就是 **組建** 資料檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-128">The first type of tenant data file in CQD is the **Building** data file.</span></span> <span data-ttu-id="c92cc-129">[子網] 欄是透過展開 [網路 + NetworkRange] 欄，然後將 [子網] 欄加入通話記錄的第一個子網或 [第二個子網] 欄，來顯示建築物、城市、國家或地區資訊。</span><span class="sxs-lookup"><span data-stu-id="c92cc-129">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="c92cc-130">您上傳的資料檔案格式，必須符合下列準則，才能在上傳前進行驗證檢查：</span><span class="sxs-lookup"><span data-stu-id="c92cc-130">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="c92cc-131">檔案必須是 tsv 檔案， (資料行是由索引標籤分隔，) 或 .csv 檔案 (欄之間以) 逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="c92cc-131">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="c92cc-132">資料檔案不包含表格標題列。</span><span class="sxs-lookup"><span data-stu-id="c92cc-132">The data file doesn't include a table header row.</span></span> <span data-ttu-id="c92cc-133">資料檔案的第一行應該是真實資料，而不是標頭標籤（例如「網路」）。</span><span class="sxs-lookup"><span data-stu-id="c92cc-133">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>

- <span data-ttu-id="c92cc-134">檔案中的資料類型只能是 String、Integer 或 Boolean。</span><span class="sxs-lookup"><span data-stu-id="c92cc-134">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="c92cc-135">針對整數資料類型，此值必須是一個數值。</span><span class="sxs-lookup"><span data-stu-id="c92cc-135">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="c92cc-136">布林值必須是0或1。</span><span class="sxs-lookup"><span data-stu-id="c92cc-136">Boolean values must be either 0 or 1.</span></span>

- <span data-ttu-id="c92cc-137">如果資料行使用 [字串] 資料類型，資料欄位可以是空的，但仍必須以 tab 或逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="c92cc-137">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="c92cc-138">空白資料欄位只會指派空的字串值。</span><span class="sxs-lookup"><span data-stu-id="c92cc-138">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="c92cc-139">每個資料列必須有15個數據行，每一欄都必須具有適當的資料類型，且欄必須按照下表所列的順序 (逗號或定位字元分隔) ：</span><span class="sxs-lookup"><span data-stu-id="c92cc-139">There must be 15 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):</span></span>

  <span data-ttu-id="c92cc-140">**建立資料檔案格式**</span><span class="sxs-lookup"><span data-stu-id="c92cc-140">**Building data file format**</span></span>
  
  | <span data-ttu-id="c92cc-141">欄名稱</span><span class="sxs-lookup"><span data-stu-id="c92cc-141">Column name</span></span>        | <span data-ttu-id="c92cc-142">資料類型</span><span class="sxs-lookup"><span data-stu-id="c92cc-142">Data type</span></span> | <span data-ttu-id="c92cc-143">範例</span><span class="sxs-lookup"><span data-stu-id="c92cc-143">Example</span></span>                   | <span data-ttu-id="c92cc-144">指導方針</span><span class="sxs-lookup"><span data-stu-id="c92cc-144">Guidance</span></span>              |
  |--------------------|-----------|---------------------------|-----------------------|
  | <span data-ttu-id="c92cc-145">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="c92cc-145">NetworkIP</span></span>          | <span data-ttu-id="c92cc-146">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-146">String</span></span>    | <span data-ttu-id="c92cc-147">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="c92cc-147">192.168.1.0</span></span>               | <span data-ttu-id="c92cc-148">必要</span><span class="sxs-lookup"><span data-stu-id="c92cc-148">Required</span></span>              |
  | <span data-ttu-id="c92cc-149">NetworkName</span><span class="sxs-lookup"><span data-stu-id="c92cc-149">NetworkName</span></span>        | <span data-ttu-id="c92cc-150">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-150">String</span></span>    | <span data-ttu-id="c92cc-151">美國/西雅圖/西雅圖-海-1</span><span class="sxs-lookup"><span data-stu-id="c92cc-151">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="c92cc-152">必要<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c92cc-152">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="c92cc-153">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="c92cc-153">NetworkRange</span></span>       | <span data-ttu-id="c92cc-154">電話</span><span class="sxs-lookup"><span data-stu-id="c92cc-154">Number</span></span>    | <span data-ttu-id="c92cc-155">26</span><span class="sxs-lookup"><span data-stu-id="c92cc-155">26</span></span>                        | <span data-ttu-id="c92cc-156">必要</span><span class="sxs-lookup"><span data-stu-id="c92cc-156">Required</span></span>              |
  | <span data-ttu-id="c92cc-157">BuildingName</span><span class="sxs-lookup"><span data-stu-id="c92cc-157">BuildingName</span></span>       | <span data-ttu-id="c92cc-158">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-158">String</span></span>    | <span data-ttu-id="c92cc-159">北京-海-1</span><span class="sxs-lookup"><span data-stu-id="c92cc-159">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="c92cc-160">必要<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c92cc-160">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="c92cc-161">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="c92cc-161">OwnershipType</span></span>      | <span data-ttu-id="c92cc-162">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-162">String</span></span>    | <span data-ttu-id="c92cc-163">尚未</span><span class="sxs-lookup"><span data-stu-id="c92cc-163">Contoso</span></span>                   | <span data-ttu-id="c92cc-164">選用</span><span class="sxs-lookup"><span data-stu-id="c92cc-164">Optional</span></span>              |
  | <span data-ttu-id="c92cc-165">BuildingType</span><span class="sxs-lookup"><span data-stu-id="c92cc-165">BuildingType</span></span>       | <span data-ttu-id="c92cc-166">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-166">String</span></span>    | <span data-ttu-id="c92cc-167">終止</span><span class="sxs-lookup"><span data-stu-id="c92cc-167">IT Termination</span></span>            | <span data-ttu-id="c92cc-168">選用</span><span class="sxs-lookup"><span data-stu-id="c92cc-168">Optional</span></span>              |
  | <span data-ttu-id="c92cc-169">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="c92cc-169">BuildingOfficeType</span></span> | <span data-ttu-id="c92cc-170">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-170">String</span></span>    | <span data-ttu-id="c92cc-171">工程學</span><span class="sxs-lookup"><span data-stu-id="c92cc-171">Engineering</span></span>               | <span data-ttu-id="c92cc-172">選用</span><span class="sxs-lookup"><span data-stu-id="c92cc-172">Optional</span></span>              |
  | <span data-ttu-id="c92cc-173">座</span><span class="sxs-lookup"><span data-stu-id="c92cc-173">City</span></span>               | <span data-ttu-id="c92cc-174">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-174">String</span></span>    | <span data-ttu-id="c92cc-175">西雅圖</span><span class="sxs-lookup"><span data-stu-id="c92cc-175">Seattle</span></span>                   | <span data-ttu-id="c92cc-176">採用</span><span class="sxs-lookup"><span data-stu-id="c92cc-176">Recommended</span></span>           |
  | <span data-ttu-id="c92cc-177">郵遞區號</span><span class="sxs-lookup"><span data-stu-id="c92cc-177">ZipCode</span></span>            | <span data-ttu-id="c92cc-178">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-178">String</span></span>    | <span data-ttu-id="c92cc-179">98001</span><span class="sxs-lookup"><span data-stu-id="c92cc-179">98001</span></span>                     | <span data-ttu-id="c92cc-180">採用</span><span class="sxs-lookup"><span data-stu-id="c92cc-180">Recommended</span></span>           |
  | <span data-ttu-id="c92cc-181">國家</span><span class="sxs-lookup"><span data-stu-id="c92cc-181">Country</span></span>            | <span data-ttu-id="c92cc-182">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-182">String</span></span>    | <span data-ttu-id="c92cc-183">一下</span><span class="sxs-lookup"><span data-stu-id="c92cc-183">US</span></span>                        | <span data-ttu-id="c92cc-184">採用</span><span class="sxs-lookup"><span data-stu-id="c92cc-184">Recommended</span></span>           |
  | <span data-ttu-id="c92cc-185">市</span><span class="sxs-lookup"><span data-stu-id="c92cc-185">State</span></span>              | <span data-ttu-id="c92cc-186">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-186">String</span></span>    | <span data-ttu-id="c92cc-187">華盛頓</span><span class="sxs-lookup"><span data-stu-id="c92cc-187">WA</span></span>                        | <span data-ttu-id="c92cc-188">採用</span><span class="sxs-lookup"><span data-stu-id="c92cc-188">Recommended</span></span>           |
  | <span data-ttu-id="c92cc-189">國家</span><span class="sxs-lookup"><span data-stu-id="c92cc-189">Region</span></span>             | <span data-ttu-id="c92cc-190">String</span><span class="sxs-lookup"><span data-stu-id="c92cc-190">String</span></span>    | <span data-ttu-id="c92cc-191">MSUS</span><span class="sxs-lookup"><span data-stu-id="c92cc-191">MSUS</span></span>                      | <span data-ttu-id="c92cc-192">採用</span><span class="sxs-lookup"><span data-stu-id="c92cc-192">Recommended</span></span>           |
  | <span data-ttu-id="c92cc-193">InsideCorp<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c92cc-193">InsideCorp<sup>2</sup></span></span>         | <span data-ttu-id="c92cc-194">Bool</span><span class="sxs-lookup"><span data-stu-id="c92cc-194">Bool</span></span>      | <span data-ttu-id="c92cc-195">1</span><span class="sxs-lookup"><span data-stu-id="c92cc-195">1</span></span>             | <span data-ttu-id="c92cc-196">必要</span><span class="sxs-lookup"><span data-stu-id="c92cc-196">Required</span></span>              |
  | <span data-ttu-id="c92cc-197">ExpressRoute<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="c92cc-197">ExpressRoute<sup>3</sup></span></span>       | <span data-ttu-id="c92cc-198">Bool</span><span class="sxs-lookup"><span data-stu-id="c92cc-198">Bool</span></span>      | <span data-ttu-id="c92cc-199">0</span><span class="sxs-lookup"><span data-stu-id="c92cc-199">0</span></span>             | <span data-ttu-id="c92cc-200">必要</span><span class="sxs-lookup"><span data-stu-id="c92cc-200">Required</span></span>              |
  | <span data-ttu-id="c92cc-201">點對點</span><span class="sxs-lookup"><span data-stu-id="c92cc-201">VPN</span></span>                | <span data-ttu-id="c92cc-202">Bool</span><span class="sxs-lookup"><span data-stu-id="c92cc-202">Bool</span></span>      | <span data-ttu-id="c92cc-203">0</span><span class="sxs-lookup"><span data-stu-id="c92cc-203">0</span></span>                         | <span data-ttu-id="c92cc-204">選用</span><span class="sxs-lookup"><span data-stu-id="c92cc-204">Optional</span></span>              |

  <span data-ttu-id="c92cc-205"><sup>1</sup> 當 CQD 不需要時，範本會設定為顯示建築物和網路名稱。</span><span class="sxs-lookup"><span data-stu-id="c92cc-205"><sup>1</sup> While not required by CQD, the templates are configured to display Building and Network name.</span></span>

  <span data-ttu-id="c92cc-206"><sup>2</sup> 這個設定可以用來反映子網上是否位於公司網路內。</span><span class="sxs-lookup"><span data-stu-id="c92cc-206"><sup>2</sup> This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="c92cc-207">您可以自訂用法以用於其他用途。</span><span class="sxs-lookup"><span data-stu-id="c92cc-207">You can customize usage for other purposes.</span></span>

  <span data-ttu-id="c92cc-208"><sup>3</sup> 這個設定可用來反映網路使用的是 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="c92cc-208"><sup>3</sup> This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="c92cc-209">您可以自訂用法以用於其他用途。</span><span class="sxs-lookup"><span data-stu-id="c92cc-209">You can customize usage for other purposes.</span></span>  

  <span data-ttu-id="c92cc-210">**範例列：**</span><span class="sxs-lookup"><span data-stu-id="c92cc-210">**Sample row:**</span></span>

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="c92cc-211">網路範圍可以用來代表幾個子網的 (supernet 組合，) 的單一路由前置詞。</span><span class="sxs-lookup"><span data-stu-id="c92cc-211">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="c92cc-212">所有新的建築物上傳都會被檢查，以取得任何重迭的範圍。</span><span class="sxs-lookup"><span data-stu-id="c92cc-212">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="c92cc-213">如果您先前上傳的是組建檔案，您應該下載目前的檔案，然後重新上傳以找出任何重疊，並修正問題，然後再重新上傳。</span><span class="sxs-lookup"><span data-stu-id="c92cc-213">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="c92cc-214">先前上傳的檔案中的任何交疊，可能會導致無法正確地將子網對應至報表中的建築物。</span><span class="sxs-lookup"><span data-stu-id="c92cc-214">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="c92cc-215">某些 VPN 實現不會精確地報告子網資訊。</span><span class="sxs-lookup"><span data-stu-id="c92cc-215">Certain VPN implementations do not accurately report the subnet information.</span></span> 
>
> <span data-ttu-id="c92cc-216">[VPN] 欄是選擇性的，預設為0。</span><span class="sxs-lookup"><span data-stu-id="c92cc-216">The VPN column is optional and will default to 0.</span></span> <span data-ttu-id="c92cc-217">如果 VPN 欄的值設為1，則該資料列所代表的子網將會完全展開，以符合子網中的所有 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c92cc-217">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="c92cc-218">請謹慎使用這個方式，然後只針對 VPN 子網，因為完全擴充這些子網會對涉及建立資料之查詢的查詢時間造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="c92cc-218">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>


### <a name="supernetting"></a><span data-ttu-id="c92cc-219">Supernetting</span><span class="sxs-lookup"><span data-stu-id="c92cc-219">Supernetting</span></span>

<span data-ttu-id="c92cc-220">您可以使用 supernetting （通常稱為無類別 Inter-Domain 路由 (CIDR），) 代替定義每個子網。</span><span class="sxs-lookup"><span data-stu-id="c92cc-220">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="c92cc-221">*Supernet* 是多個子網的組合，可共用單一路由前置詞。</span><span class="sxs-lookup"><span data-stu-id="c92cc-221">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="c92cc-222">您可以使用 supernetted 位址，而不是為每個子網新增專案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-222">Instead of adding an entry for each subnet, you can use the supernetted address.</span></span> <span data-ttu-id="c92cc-223">支援 Supernetting，但我們不建議使用它。</span><span class="sxs-lookup"><span data-stu-id="c92cc-223">Supernetting is supported, but we don't recommend using it.</span></span>

<span data-ttu-id="c92cc-224">例如，Contoso 的行銷大樓是由下列子網組成：</span><span class="sxs-lookup"><span data-stu-id="c92cc-224">For example, Contoso's marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="c92cc-225">10.1.0.0/24-第一層</span><span class="sxs-lookup"><span data-stu-id="c92cc-225">10.1.0.0/24—first floor</span></span>
-   <span data-ttu-id="c92cc-226">10.1.1.0/24-第二層</span><span class="sxs-lookup"><span data-stu-id="c92cc-226">10.1.1.0/24—second floor</span></span>
-   <span data-ttu-id="c92cc-227">10.1.2.0/24-第三層</span><span class="sxs-lookup"><span data-stu-id="c92cc-227">10.1.2.0/24—third floor</span></span>
-   <span data-ttu-id="c92cc-228">10.1.3.0/24-第四層</span><span class="sxs-lookup"><span data-stu-id="c92cc-228">10.1.3.0/24—fourth floor</span></span>

<span data-ttu-id="c92cc-229">您可以使用 supernetted 位址（在此範例中為 10.1.0.0/22），而不是為每個子網上新增專案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-229">Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="c92cc-230">Network = 10.1.0。0</span><span class="sxs-lookup"><span data-stu-id="c92cc-230">Network = 10.1.0.0</span></span>
-   <span data-ttu-id="c92cc-231">網路範圍 = 22</span><span class="sxs-lookup"><span data-stu-id="c92cc-231">Network Range = 22</span></span>

<span data-ttu-id="c92cc-232">在執行 supernetting 之前，請先考慮以下幾點：</span><span class="sxs-lookup"><span data-stu-id="c92cc-232">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="c92cc-233">Supernetting 只能在含有8位到28位元遮罩的子網對應中使用。</span><span class="sxs-lookup"><span data-stu-id="c92cc-233">Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="c92cc-234">Supernetting 佔用較少的時間，但代價是減少資料的豐富程度。</span><span class="sxs-lookup"><span data-stu-id="c92cc-234">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="c92cc-235">假設有一個涉及子網10.1.2.0 的品質問題。</span><span class="sxs-lookup"><span data-stu-id="c92cc-235">Let's say there's a quality problem involving subnet 10.1.2.0.</span></span> <span data-ttu-id="c92cc-236">如果您已執行 supernetting，就不會知道組建子網上的位置，或是它所 (的網路類型（例如，實驗室) ）。</span><span class="sxs-lookup"><span data-stu-id="c92cc-236">If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="c92cc-237">如果您已定義所有子網，以取得建築物和上傳的樓層位置資訊，您就可以看到這種差異。</span><span class="sxs-lookup"><span data-stu-id="c92cc-237">If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.</span></span>

-   <span data-ttu-id="c92cc-238">務必確保 supernetted 位址正確無誤，而且不會捕捉不想要的子網。</span><span class="sxs-lookup"><span data-stu-id="c92cc-238">It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.</span></span>

-   <span data-ttu-id="c92cc-239">在資料中找到192.168.0.0 是很常見的。</span><span class="sxs-lookup"><span data-stu-id="c92cc-239">It's quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="c92cc-240">對於許多組織而言，這表示使用者是在家中。</span><span class="sxs-lookup"><span data-stu-id="c92cc-240">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="c92cc-241">對其他人而言，這是衛星辦公室的 IP 位址配置。</span><span class="sxs-lookup"><span data-stu-id="c92cc-241">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="c92cc-242">如果您的組織有使用這項設定的辦事處，請不要將它納入您的組建檔案中，因為很難使用 [通用子網](quality-of-experience-review-guide.md#common-subnets)來區分家用和內部網路。</span><span class="sxs-lookup"><span data-stu-id="c92cc-242">If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide.md#common-subnets).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c92cc-243">網路範圍可以用來代表 supernet。</span><span class="sxs-lookup"><span data-stu-id="c92cc-243">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="c92cc-244">所有新的組建資料檔案上傳都將會檢查任何重迭的範圍。</span><span class="sxs-lookup"><span data-stu-id="c92cc-244">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="c92cc-245">如果您先前上傳的是組建檔案，您應該下載目前的檔案並再次上傳，以找出任何重迭並修正問題。</span><span class="sxs-lookup"><span data-stu-id="c92cc-245">If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="c92cc-246">先前上傳的檔案中的任何交疊，可能會導致無法正確地將子網對應至報表中的建築物。</span><span class="sxs-lookup"><span data-stu-id="c92cc-246">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span>

### <a name="vpn"></a><span data-ttu-id="c92cc-247">點對點</span><span class="sxs-lookup"><span data-stu-id="c92cc-247">VPN</span></span>

<span data-ttu-id="c92cc-248">當用戶端傳送至 Microsoft 365 或 Office 365 的 QoE) 資料（包括 VPN 標誌）時， (的體驗品質。</span><span class="sxs-lookup"><span data-stu-id="c92cc-248">The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="c92cc-249">CQD 將會看到此為第一個 VPN 和第二個 VPN 維度。</span><span class="sxs-lookup"><span data-stu-id="c92cc-249">CQD will see this as the First VPN and Second VPN dimensions.</span></span> <span data-ttu-id="c92cc-250">不過，此標記會依賴 VPN 廠商的報告來向 Windows 確認 VPN 網路介面卡已註冊為遠端存取配接器。</span><span class="sxs-lookup"><span data-stu-id="c92cc-250">However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="c92cc-251">並非所有的 VPN 供應商都正確註冊遠端存取配接器。</span><span class="sxs-lookup"><span data-stu-id="c92cc-251">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="c92cc-252">因此，您可能無法使用內建的 VPN 查詢篩選。</span><span class="sxs-lookup"><span data-stu-id="c92cc-252">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="c92cc-253">使用上述所述的 VPN 欄來精確標示及識別 VPN 子網。</span><span class="sxs-lookup"><span data-stu-id="c92cc-253">Use the VPN column discussed above to accurately mark and identify VPN subnets.</span></span> <span data-ttu-id="c92cc-254">為您的 VPN 網路加上標籤，以便在報表中輕鬆識別。</span><span class="sxs-lookup"><span data-stu-id="c92cc-254">It is also good practice to label your VPN networks for easy identification in your reports.</span></span> <span data-ttu-id="c92cc-255">以下是兩個如何標示 VPN 子網的範例：</span><span class="sxs-lookup"><span data-stu-id="c92cc-255">Below are two examples of how to label your VPN subnets:</span></span>

- <span data-ttu-id="c92cc-256">在這個 [VPN 子網] 欄位中輸入「VPN」，以定義 **網路名稱** 。</span><span class="sxs-lookup"><span data-stu-id="c92cc-256">Define a **Network Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![使用網路名稱顯示 VPN 的 QCD 報告螢幕擷取畫面](media/qerguide-image-vpnnetworkname.png)

- <span data-ttu-id="c92cc-258">在這個 [VPN 子網] 欄位中輸入「VPN」來定義 **建築物名稱** 。</span><span class="sxs-lookup"><span data-stu-id="c92cc-258">Define a **Building Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![使用建築物名稱顯示 VPN 的 QCD 報告螢幕擷取畫面](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> <span data-ttu-id="c92cc-260">當基礎連線是無線時，已知 VPN 連線是將網路連線類型 misidentify 為有線。</span><span class="sxs-lookup"><span data-stu-id="c92cc-260">VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless.</span></span> <span data-ttu-id="c92cc-261">當您以 VPN 連線查看品質時，您無法假設正確識別了連線類型。</span><span class="sxs-lookup"><span data-stu-id="c92cc-261">When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.</span></span>

## <a name="endpoint-data-file"></a><span data-ttu-id="c92cc-262">端點資料檔案</span><span class="sxs-lookup"><span data-stu-id="c92cc-262">Endpoint data file</span></span>

<span data-ttu-id="c92cc-263">另一種類型的 CQD 租使用者資料檔案是 **端點** 資料檔。</span><span class="sxs-lookup"><span data-stu-id="c92cc-263">The other type of CQD tenant data file is the **Endpoint** data file.</span></span> <span data-ttu-id="c92cc-264">欄值會用於通話記錄的第一個用戶端端點名稱或第二個用戶端端點名稱欄，以顯示端點、模型或類型資訊。</span><span class="sxs-lookup"><span data-stu-id="c92cc-264">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="c92cc-265">您上傳的資料檔案格式，必須符合下列準則，才能在上傳前進行驗證檢查：</span><span class="sxs-lookup"><span data-stu-id="c92cc-265">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="c92cc-266">檔案必須是 tsv 檔案， (資料行是由索引標籤分隔，) 或 .csv 檔案 (欄之間以) 逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="c92cc-266">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="c92cc-267">資料檔案的內容不會包含表格標題。</span><span class="sxs-lookup"><span data-stu-id="c92cc-267">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="c92cc-268">資料檔案的第一行應該是真實資料，而不是像是 "終結點" 這樣的標頭標籤。</span><span class="sxs-lookup"><span data-stu-id="c92cc-268">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>

- <span data-ttu-id="c92cc-269">所有七個數據列都只使用字串資料類型。</span><span class="sxs-lookup"><span data-stu-id="c92cc-269">All seven columns use the String data type only.</span></span> <span data-ttu-id="c92cc-270">允許的最大長度為64個字元。</span><span class="sxs-lookup"><span data-stu-id="c92cc-270">The maximum allowed length is 64 characters.</span></span>

- <span data-ttu-id="c92cc-271">資料欄位可以是空的，但仍須以 tab 或逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="c92cc-271">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="c92cc-272">空白資料欄位只會指派空的字串值。</span><span class="sxs-lookup"><span data-stu-id="c92cc-272">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="c92cc-273">終結點必須是唯一的，否則上傳就會失敗。</span><span class="sxs-lookup"><span data-stu-id="c92cc-273">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="c92cc-274">如果有重複的資料列，或是兩列使用相同的終結點，衝突將會導致不正確的聯接。</span><span class="sxs-lookup"><span data-stu-id="c92cc-274">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>

- <span data-ttu-id="c92cc-275">EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自訂的標籤。</span><span class="sxs-lookup"><span data-stu-id="c92cc-275">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="c92cc-276">它們可以是空白字串或 "IT 部門指派2018膝上型電腦" 或 "資產標記 5678" 等值。</span><span class="sxs-lookup"><span data-stu-id="c92cc-276">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>

- <span data-ttu-id="c92cc-277">每個資料列必須有七個數據行，且欄必須以下列順序排列：</span><span class="sxs-lookup"><span data-stu-id="c92cc-277">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="c92cc-278">**欄位順序：**</span><span class="sxs-lookup"><span data-stu-id="c92cc-278">**Field order:**</span></span>

  <span data-ttu-id="c92cc-279">終結點、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="c92cc-279">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="c92cc-280">**範例列：**</span><span class="sxs-lookup"><span data-stu-id="c92cc-280">**Sample row:**</span></span>

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`


## <a name="update-a-building-file"></a><span data-ttu-id="c92cc-281">更新組建檔案</span><span class="sxs-lookup"><span data-stu-id="c92cc-281">Update a building file</span></span>

<span data-ttu-id="c92cc-282">在收集建立和子網資訊時，系統管理員會經常在一段時間內，在多個反覆運算中上傳檔案，並在新的子網變為可用時，新增其建築物資訊。</span><span class="sxs-lookup"><span data-stu-id="c92cc-282">While gathering building and subnet information, administrators will often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available.</span></span> <span data-ttu-id="c92cc-283">發生這種情況時，您必須重新上傳您的組建檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-283">When this occurs, you'll need to re-upload your building file.</span></span> <span data-ttu-id="c92cc-284">此程式就像上一節所述的初始上傳一樣，還有一些例外狀況，如下一節所述。</span><span class="sxs-lookup"><span data-stu-id="c92cc-284">This process is like the initial upload as described in the previous section, with a few exceptions as noted in the following section.</span></span>

> [!Important]
> <span data-ttu-id="c92cc-285">一次只能有一個建立檔。</span><span class="sxs-lookup"><span data-stu-id="c92cc-285">Only one building file can be active at a time.</span></span> <span data-ttu-id="c92cc-286">多個建築物檔案不是累加的。</span><span class="sxs-lookup"><span data-stu-id="c92cc-286">Multiple building files aren't cumulative.</span></span>

## <a name="add-net-new-subnets"></a><span data-ttu-id="c92cc-287">新增全新子網</span><span class="sxs-lookup"><span data-stu-id="c92cc-287">Add net new subnets</span></span>

<span data-ttu-id="c92cc-288">在某些情況下，您需要將全新的子網新增至 CQD，而不是原本是您的網路拓朴的一部分。</span><span class="sxs-lookup"><span data-stu-id="c92cc-288">There are times when you'll need to add net new subnets to CQD that weren't originally part of your network topology.</span></span> <span data-ttu-id="c92cc-289">若要新增 net 新建子網，請在 CQD 中的 **租使用者資料上傳** 頁面執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c92cc-289">To add net new subnets, do the following from the **Tenant Data Upload** page in CQD:</span></span>

1.  <span data-ttu-id="c92cc-290">如果您還沒有最新的複本，請下載原始檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-290">Download the original file, if you don't already have an up-to-date copy.</span></span>

1.  <span data-ttu-id="c92cc-291">在 CQD 中移除目前的檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-291">Remove the current file in CQD.</span></span>

1.  <span data-ttu-id="c92cc-292">編輯原始的組建檔案，並提供至少在取得網路新子網前一天的結束日期。</span><span class="sxs-lookup"><span data-stu-id="c92cc-292">Edit the original building file and provide an end date that occurs at least one day before the net new subnets were acquired.</span></span>

1.  <span data-ttu-id="c92cc-293">將全新的子網附加至原始的組建檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-293">Append the net new subnets to the original building file.</span></span>

1.  <span data-ttu-id="c92cc-294">上傳新修改的組建檔案，並在前一個建築物檔案結束後的一天中設定開始日期。</span><span class="sxs-lookup"><span data-stu-id="c92cc-294">Upload the newly modified building file, and set the start date for one day after the previous building file ends.</span></span>

## <a name="add-missing-subnets"></a><span data-ttu-id="c92cc-295">新增遺失的子網</span><span class="sxs-lookup"><span data-stu-id="c92cc-295">Add missing subnets</span></span>

<span data-ttu-id="c92cc-296">在您上傳受管理的網路的建築物資訊之後，每個受管理的網路都應該有一個建築物關聯。</span><span class="sxs-lookup"><span data-stu-id="c92cc-296">After you upload building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="c92cc-297">不過，這不一定是案例;通常會錯過幾個子網。</span><span class="sxs-lookup"><span data-stu-id="c92cc-297">However, this won't always be the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="c92cc-298">若要找出這些缺少的網路，請在 CQD 中查看 [**經驗品質報告**] 頁面上的 [**遺失的子網報告**]。</span><span class="sxs-lookup"><span data-stu-id="c92cc-298">To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD.</span></span> <span data-ttu-id="c92cc-299">這會顯示有10個以上的音訊資料流程的所有子網，且未在建築物資料檔中定義，且標示為外部。</span><span class="sxs-lookup"><span data-stu-id="c92cc-299">This presents all the subnets with 10 or more audio streams that aren't defined in the building data file and are being marked as outside.</span></span> <span data-ttu-id="c92cc-300">確定此清單中沒有受管理的網路。</span><span class="sxs-lookup"><span data-stu-id="c92cc-300">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="c92cc-301">如果子網遺失，請使用下列程式來更新原始的組建資料檔，並將它重新上傳到 CQD。</span><span class="sxs-lookup"><span data-stu-id="c92cc-301">If subnets are missing, use the following procedure to update the original building data file and re-upload it to CQD.</span></span>

1. <span data-ttu-id="c92cc-302">移至 CQD 中的 **租使用者資料上傳** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c92cc-302">Go to the **Tenant Data Upload** page in CQD.</span></span>

1. <span data-ttu-id="c92cc-303">如果您還沒有最新的複本，請下載原始檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-303">Download the original file, if you don't already have an up-to-date copy.</span></span>

1. <span data-ttu-id="c92cc-304">在 CQD 中移除目前的檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-304">Remove the current file in CQD.</span></span>

1. <span data-ttu-id="c92cc-305">將新的子網附加至原始檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-305">Append the new subnets to the original file.</span></span>

1. <span data-ttu-id="c92cc-306">上傳組建檔案。</span><span class="sxs-lookup"><span data-stu-id="c92cc-306">Upload the building file.</span></span> <span data-ttu-id="c92cc-307">請務必先將開始日期設為至少八個月，以便 CQD 會處理歷史資料。</span><span class="sxs-lookup"><span data-stu-id="c92cc-307">Be sure to set the start date to at least eight months prior so that CQD will process historical data.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c92cc-308">您必須將您的租使用者識別碼，作為 **第二個租使用者識別碼** 的查詢篩選器新增至此報告，以篩選報表，以便只查看貴組織的租使用者資料。</span><span class="sxs-lookup"><span data-stu-id="c92cc-308">You'll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization's tenant data.</span></span> <span data-ttu-id="c92cc-309">否則，報表就會顯示聯盟子網。</span><span class="sxs-lookup"><span data-stu-id="c92cc-309">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="c92cc-310">請務必將 [月年度] 報表篩選調整為 [本月]。</span><span class="sxs-lookup"><span data-stu-id="c92cc-310">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="c92cc-311">選取 [ **編輯**]，然後調整 [ **月** ] 報表篩選，以儲存新的預設月份。</span><span class="sxs-lookup"><span data-stu-id="c92cc-311">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c92cc-312">相關主題</span><span class="sxs-lookup"><span data-stu-id="c92cc-312">Related topics</span></span>

[<span data-ttu-id="c92cc-313">建立 CQD 的建立地圖</span><span class="sxs-lookup"><span data-stu-id="c92cc-313">Create a building map for CQD</span></span>](CQD-building-mapping.md)

[<span data-ttu-id="c92cc-314">改善及監視團隊的通話品質</span><span class="sxs-lookup"><span data-stu-id="c92cc-314">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="c92cc-315">什麼是 CQD？</span><span class="sxs-lookup"><span data-stu-id="c92cc-315">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="c92cc-316">設定通話品質儀表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="c92cc-316">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="c92cc-317">CQD 資料和報表</span><span class="sxs-lookup"><span data-stu-id="c92cc-317">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="c92cc-318">使用 CQD 管理通話與會議品質</span><span class="sxs-lookup"><span data-stu-id="c92cc-318">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="c92cc-319">CQD 中可用的維度與量值</span><span class="sxs-lookup"><span data-stu-id="c92cc-319">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="c92cc-320">CQD 中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="c92cc-320">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="c92cc-321">使用 Power BI 來分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="c92cc-321">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
