---
title: Lync Server 2013： 管理通訊錄服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72d08d786f41dc606b419f9452970d683b8da37
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="b17a1-102">管理 Lync Server 2013 中的通訊錄服務</span><span class="sxs-lookup"><span data-stu-id="b17a1-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b17a1-103">_**上次修改主題：** 2014年-02-05_</span><span class="sxs-lookup"><span data-stu-id="b17a1-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="b17a1-104">部署 Lync Server，Enterprise Edition 或 Standard Edition server 的一部分，預設會安裝通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="b17a1-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="b17a1-105">通訊錄服務 – RTCab – 所使用的資料庫建立 SQL Server 上 (這是後端 SQL Server Enterprise Edition，; Standard Edition server，組合的 SQL 伺服器)。</span><span class="sxs-lookup"><span data-stu-id="b17a1-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b17a1-106">如需使用<STRONG>Adsi</STRONG>編輯 Active Directory 網域服務物件的屬性的詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/?linkid=330427">Adsi 編輯器]</A>。</span><span class="sxs-lookup"><span data-stu-id="b17a1-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="b17a1-107">特別針對通訊錄服務 Resource kit 工具的詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit 工具</A>。</span><span class="sxs-lookup"><span data-stu-id="b17a1-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="b17a1-108">Address Book Server 電話號碼正規化</span><span class="sxs-lookup"><span data-stu-id="b17a1-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="b17a1-109">Lync Server 需要標準化的 RFC 3966/E.164 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b17a1-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="b17a1-110">若要使用非結構化或不一致的格式化的電話號碼，Lync Server 依賴 Address Book Server 之前他們所要的正規化規則交給預先處理的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b17a1-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="b17a1-111">當通訊錄中使用的電話號碼正規化規則會套用，例如 Lync Phone Edition 和 Lync 行動用戶端可以使用這些正規化的號碼。</span><span class="sxs-lookup"><span data-stu-id="b17a1-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="b17a1-p104">舊版中使用的正規化規則可能需要經過一些調整才能正常使用。因為在交給正規化規則之前會先移除空格和非強制字元，所以如果 regex 運算式明確尋找虛線或其他已移除的字元，正規化規則可能會失敗。您應該檢閱正規化規則，確保它們不會尋找這類非強制字元，否則，如果規則預期字元存在而字元不存在，規則就會先按正常程序失敗再繼續運作。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="b17a1-115">使用者複寫器和 Address Book Server</span><span class="sxs-lookup"><span data-stu-id="b17a1-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="b17a1-116">Address Book Server 會使用 [使用者複寫器] 提供的資料，來更新其最初從全域通訊清單 (GAL) 取得的資訊。</span><span class="sxs-lookup"><span data-stu-id="b17a1-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="b17a1-117">使用者複寫器寫入每個使用者、 連絡人及群組到 AbUserEntry 資料庫資料表中的 Active Directory 網域服務屬性和 Address Book Server 會同步到檔案中的 Address Book Server 檔案存放區資料庫中的使用者資料和通訊錄中輸入資料庫 RTCab。</span><span class="sxs-lookup"><span data-stu-id="b17a1-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="b17a1-118">AbUserEntry 資料表的架構使用兩個資料行 **UserGuid** 和 **UserData**。</span><span class="sxs-lookup"><span data-stu-id="b17a1-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="b17a1-119">**UserGuid**是在索引資料欄，並包含 Active Directory 物件的 16 位元組 GUID。</span><span class="sxs-lookup"><span data-stu-id="b17a1-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="b17a1-120">**UserData**為影像資料行包含的所有連絡人的先前所述的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="b17a1-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="b17a1-121">使用者複寫器會決定藉由讀取組態資料表位於相同的 SQL server 執行個體作為 AbUserEntry 表格來撰寫哪些 Active Directory 屬性。</span><span class="sxs-lookup"><span data-stu-id="b17a1-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="b17a1-122">AbAttribute 資料表包含三個資料行 **ID**、**Name**、**Flags** 和 **Enable**。</span><span class="sxs-lookup"><span data-stu-id="b17a1-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="b17a1-123">此資料表是在資料庫設定期間建立。</span><span class="sxs-lookup"><span data-stu-id="b17a1-123">The table is created during database setup.</span></span> <span data-ttu-id="b17a1-124">如果 AbAttribute 資料表是空的，[使用者複寫器] 會略過其 AbUserEntry 資料表處理邏輯。</span><span class="sxs-lookup"><span data-stu-id="b17a1-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="b17a1-125">Address Book Server 屬性是從 AbAttribute 資料表擷取的動態屬性，該資料表最初是在 Address Book Server 啟動時由 Address Book Server 寫入。</span><span class="sxs-lookup"><span data-stu-id="b17a1-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="b17a1-126">Address Book Server 啟用填入 AbAttribute 表格，如下表所示的值。</span><span class="sxs-lookup"><span data-stu-id="b17a1-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b17a1-127">識別碼</span><span class="sxs-lookup"><span data-stu-id="b17a1-127">ID</span></span></th>
<th><span data-ttu-id="b17a1-128">名稱</span><span class="sxs-lookup"><span data-stu-id="b17a1-128">Name</span></span></th>
<th><span data-ttu-id="b17a1-129">Flags</span><span class="sxs-lookup"><span data-stu-id="b17a1-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-130">1</span><span class="sxs-lookup"><span data-stu-id="b17a1-130">1</span></span></p></td>
<td><p><span data-ttu-id="b17a1-131">givenName</span><span class="sxs-lookup"><span data-stu-id="b17a1-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="b17a1-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="b17a1-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-133">2</span><span class="sxs-lookup"><span data-stu-id="b17a1-133">2</span></span></p></td>
<td><p><span data-ttu-id="b17a1-134">Sn</span><span class="sxs-lookup"><span data-stu-id="b17a1-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="b17a1-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="b17a1-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-136">3</span><span class="sxs-lookup"><span data-stu-id="b17a1-136">3</span></span></p></td>
<td><p><span data-ttu-id="b17a1-137">displayName</span><span class="sxs-lookup"><span data-stu-id="b17a1-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="b17a1-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="b17a1-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-139">4</span><span class="sxs-lookup"><span data-stu-id="b17a1-139">4</span></span></p></td>
<td><p><span data-ttu-id="b17a1-140">標題</span><span class="sxs-lookup"><span data-stu-id="b17a1-140">Title</span></span></p></td>
<td><p><span data-ttu-id="b17a1-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="b17a1-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-142">5</span><span class="sxs-lookup"><span data-stu-id="b17a1-142">5</span></span></p></td>
<td><p><span data-ttu-id="b17a1-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="b17a1-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="b17a1-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="b17a1-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-145">6 </span><span class="sxs-lookup"><span data-stu-id="b17a1-145">6</span></span></p></td>
<td><p><span data-ttu-id="b17a1-146">Company</span><span class="sxs-lookup"><span data-stu-id="b17a1-146">Company</span></span></p></td>
<td><p><span data-ttu-id="b17a1-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="b17a1-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-148">7 </span><span class="sxs-lookup"><span data-stu-id="b17a1-148">7</span></span></p></td>
<td><p><span data-ttu-id="b17a1-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="b17a1-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="b17a1-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="b17a1-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-151">8 </span><span class="sxs-lookup"><span data-stu-id="b17a1-151">8</span></span></p></td>
<td><p><span data-ttu-id="b17a1-152">包含 PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="b17a1-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="b17a1-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="b17a1-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-154">9 </span><span class="sxs-lookup"><span data-stu-id="b17a1-154">9</span></span></p></td>
<td><p><span data-ttu-id="b17a1-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="b17a1-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="b17a1-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="b17a1-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-157">10 </span><span class="sxs-lookup"><span data-stu-id="b17a1-157">10</span></span></p></td>
<td><p><span data-ttu-id="b17a1-158">住家電話</span><span class="sxs-lookup"><span data-stu-id="b17a1-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="b17a1-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="b17a1-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-160">11 </span><span class="sxs-lookup"><span data-stu-id="b17a1-160">11</span></span></p></td>
<td><p><span data-ttu-id="b17a1-161">行動裝置</span><span class="sxs-lookup"><span data-stu-id="b17a1-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="b17a1-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="b17a1-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-163">12</span><span class="sxs-lookup"><span data-stu-id="b17a1-163">12</span></span></p></td>
<td><p><span data-ttu-id="b17a1-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="b17a1-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="b17a1-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="b17a1-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-166">13 </span><span class="sxs-lookup"><span data-stu-id="b17a1-166">13</span></span></p></td>
<td><p><span data-ttu-id="b17a1-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="b17a1-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="b17a1-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="b17a1-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-169">14 </span><span class="sxs-lookup"><span data-stu-id="b17a1-169">14</span></span></p></td>
<td><p><span data-ttu-id="b17a1-170">郵件</span><span class="sxs-lookup"><span data-stu-id="b17a1-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="b17a1-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="b17a1-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-172">15 </span><span class="sxs-lookup"><span data-stu-id="b17a1-172">15</span></span></p></td>
<td><p><span data-ttu-id="b17a1-173">groupType</span><span class="sxs-lookup"><span data-stu-id="b17a1-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="b17a1-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="b17a1-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-175">16 </span><span class="sxs-lookup"><span data-stu-id="b17a1-175">16</span></span></p></td>
<td><p><span data-ttu-id="b17a1-176">部門</span><span class="sxs-lookup"><span data-stu-id="b17a1-176">Department</span></span></p></td>
<td><p><span data-ttu-id="b17a1-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="b17a1-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-178">17 </span><span class="sxs-lookup"><span data-stu-id="b17a1-178">17</span></span></p></td>
<td><p><span data-ttu-id="b17a1-179">說明</span><span class="sxs-lookup"><span data-stu-id="b17a1-179">Description</span></span></p></td>
<td><p><span data-ttu-id="b17a1-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="b17a1-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-181">18 </span><span class="sxs-lookup"><span data-stu-id="b17a1-181">18</span></span></p></td>
<td><p><span data-ttu-id="b17a1-182">管理員</span><span class="sxs-lookup"><span data-stu-id="b17a1-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="b17a1-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="b17a1-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-184">19</span><span class="sxs-lookup"><span data-stu-id="b17a1-184">19</span></span></p></td>
<td><p><span data-ttu-id="b17a1-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="b17a1-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="b17a1-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="b17a1-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-187">20</span><span class="sxs-lookup"><span data-stu-id="b17a1-187">20</span></span></p></td>
<td><p><span data-ttu-id="b17a1-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="b17a1-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="b17a1-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="b17a1-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-190">99</span><span class="sxs-lookup"><span data-stu-id="b17a1-190">99</span></span></p></td>
<td><p><span data-ttu-id="b17a1-191">entryID</span><span class="sxs-lookup"><span data-stu-id="b17a1-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="b17a1-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="b17a1-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b17a1-193">**ID** 資料行中的數字必須是唯一的，且絕不可重複使用。</span><span class="sxs-lookup"><span data-stu-id="b17a1-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="b17a1-194">另外，保持 ID 值小於 256 可在 Address Book Server 寫入的輸出檔中節省空間。</span><span class="sxs-lookup"><span data-stu-id="b17a1-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="b17a1-195">不過，ID 最大值是 65535。</span><span class="sxs-lookup"><span data-stu-id="b17a1-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="b17a1-196">[**名稱**] 欄會對應至使用者複寫器應該放 AbUserEntry 資料表中的每個連絡人的 Active Directory 屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="b17a1-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="b17a1-197">**Flags** 資料行中的值用來定義屬性的類型。</span><span class="sxs-lookup"><span data-stu-id="b17a1-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="b17a1-198">[使用者複寫器] 認得下列類型的 Address Book Server 屬性 (以 **Flags** 資料行中的值的低位元組表示)。</span><span class="sxs-lookup"><span data-stu-id="b17a1-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b17a1-199">屬性</span><span class="sxs-lookup"><span data-stu-id="b17a1-199">Attribute</span></span></th>
<th><span data-ttu-id="b17a1-200">描述</span><span class="sxs-lookup"><span data-stu-id="b17a1-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-201">0x0</span><span class="sxs-lookup"><span data-stu-id="b17a1-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p108">字串屬性。[使用者複寫器] 會先將此類型轉換為 UTF-8，再將之儲存於 AbUserEntry 資料表。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-204">0x1</span><span class="sxs-lookup"><span data-stu-id="b17a1-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p109">二進位屬性。[使用者複寫器] 會以二進位大型物件儲存此屬性而不做任何轉換。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-207">0x2</span><span class="sxs-lookup"><span data-stu-id="b17a1-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="b17a1-208">字串屬性，但時才包含屬性值開頭&quot;tel:&quot;。</span><span class="sxs-lookup"><span data-stu-id="b17a1-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="b17a1-209">這主要用於多重值字串屬性，特別是 <strong>proxyAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="b17a1-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="b17a1-210">在此情況下，Address Book Server 會有興趣僅開頭的<strong>proxyAddresses</strong>項目&quot;tel:&quot;。</span><span class="sxs-lookup"><span data-stu-id="b17a1-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="b17a1-211">因此，以儲存空間，使用者複寫器會儲存開頭的項目&quot;tel:&quot;。</span><span class="sxs-lookup"><span data-stu-id="b17a1-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-212">0x3</span><span class="sxs-lookup"><span data-stu-id="b17a1-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p111">布林字串屬性，TRUE 會使 [使用者複寫器] 不將此連絡人放入 AbUserEntry 資料表中。如果是 FALSE，則會使 [使用者複寫器] 將此連絡人的屬性放入 AbUserEntry 資料表中，但不包括具有此旗標的特定屬性。這是另一個主要用於 <strong>msExchHideFromAddressLists</strong> 屬性的特殊案例類型。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-216">0x4</span><span class="sxs-lookup"><span data-stu-id="b17a1-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="b17a1-217">字串屬性，但時才包含屬性值開頭&quot;smtp:&quot; ，並包含&quot; @ &quot;符號。</span><span class="sxs-lookup"><span data-stu-id="b17a1-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-218">0x5</span><span class="sxs-lookup"><span data-stu-id="b17a1-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="b17a1-219">字串屬性，但時才包含屬性值開頭為&quot;tel:&quot;或&quot;smtp:&quot; ，並包含&quot; @ &quot;符號。</span><span class="sxs-lookup"><span data-stu-id="b17a1-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-220">0x100</span><span class="sxs-lookup"><span data-stu-id="b17a1-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="b17a1-221">如果設定，則這是可針對每個連絡人出現一次以上的多重值屬性。</span><span class="sxs-lookup"><span data-stu-id="b17a1-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-222">0x400</span><span class="sxs-lookup"><span data-stu-id="b17a1-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p112">如果設定，則這將識別連絡人的電子郵件使用者帳戶名稱屬性。Address Book Server 會使用此旗標來識別要在電話正規化事件記錄項目中顯示的屬性值。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-225">0x800</span><span class="sxs-lookup"><span data-stu-id="b17a1-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p113">如果設定，則這將識別連絡人的必要屬性。只有當此屬性在 Active Directory 中有值時，Address Book Server 才會在 AbUserEntry 資料表中加入使用者。如果有一個以上的必要屬性，則只要其中一個有值，就會在 AbUserEntry 資料表中加入使用者。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-229">0x1000 時相同</span><span class="sxs-lookup"><span data-stu-id="b17a1-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="b17a1-230">如果設定，則 Address Book Server 一律會正規化此屬性的值。</span><span class="sxs-lookup"><span data-stu-id="b17a1-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="b17a1-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="b17a1-232">如果設定，則當 <strong>UseNormalizationRules</strong> CMS 設定為 FALSE 時，Address Book Server 會使用 <strong>proxyAddresses</strong> 中的正規化數字，否則其行為與旗標位元為 0x1000 時相同。</span><span class="sxs-lookup"><span data-stu-id="b17a1-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="b17a1-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p114">如果設定，則 Address Book Server 不會在 AbUserEntry 資料表中加入所指定的屬性為此值的物件。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 屬性已設定此旗標位元，則不會將具有此屬性的連絡人寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="b17a1-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p115">如果設定，則 Address Book Server 不會將所指定的屬性不是此值的物件加入 AbUserEntry 資料表。如果物件上同時設定 0x4000 和 0x8000 旗標位元，則以旗標位元值設為 0x4000 的屬性為優先，且會從 AbUserEntry 資料表中排除物件。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="b17a1-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p116">如果設定，則這代表群組物件。[使用者複寫器] 會使用此旗標位元來加入具有 <strong>groupType</strong> 屬性 (表示這是群組) 的連絡人，例如，通訊群組清單或安全性群組。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="b17a1-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="b17a1-243">如果設定，則 [使用者複寫器] 會使用此旗標位元將此屬性加入裝置特定 Address Book Server 檔案 (副檔名為 .dabs 的檔案)。</span><span class="sxs-lookup"><span data-stu-id="b17a1-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b17a1-244">在舊版的 Lync Server，將變更套用至 Active Directory 時，系統管理員就必須執行**更新-CSUserDatabase**與**更新 – CSAddressBook** Windows PowerShell cmdlet 可立即保存 RTCab 資料庫與 Lync Server 使用者資料庫的變更。</span><span class="sxs-lookup"><span data-stu-id="b17a1-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="b17a1-245">在 Lync Server 2013 中，Lync Server 使用者複寫器會挑選來自 Active Directory 所做的變更，並更新 Lync Server 使用者資料庫，根據設定的間隔。</span><span class="sxs-lookup"><span data-stu-id="b17a1-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="b17a1-246">Lync Server 使用者複寫器會也將變更傳播到 RTCab 資料庫快速而不必執行 Update-csaddressbook 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="b17a1-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="b17a1-247">如果已啟用地址通訊錄 Web 查詢，然後所做的變更會反映在搜尋結果中 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b17a1-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="b17a1-248">系統管理員只將必須重新執行 Update-csaddressbook，如果已啟用 Address Book 檔案下載。</span><span class="sxs-lookup"><span data-stu-id="b17a1-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b17a1-249">根據預設 Lync Server 使用者複寫器會自動執行每隔 5 分鐘。</span><span class="sxs-lookup"><span data-stu-id="b17a1-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="b17a1-250">您可以使用 Set CSUserReplicatorConfiguration 來設定此間隔-ReplicationCycleInterval &lt; &gt;。</span><span class="sxs-lookup"><span data-stu-id="b17a1-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="b17a1-251">篩選通訊錄</span><span class="sxs-lookup"><span data-stu-id="b17a1-251">Filtering the Address Book</span></span>

<span data-ttu-id="b17a1-252">您可以根據 AbAttribute 表所列的特定 Active Directory 網域服務屬性控制填入 Address Book Server 檔案中的使用者。</span><span class="sxs-lookup"><span data-stu-id="b17a1-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="b17a1-253">其中一個這類可用於篩選的屬性就是 **msExchangeHideFromAddressBook** 屬性。</span><span class="sxs-lookup"><span data-stu-id="b17a1-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="b17a1-254">這是由 Exchange 架構所新增的使用者屬性。</span><span class="sxs-lookup"><span data-stu-id="b17a1-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="b17a1-255">如果此屬性的值是 TRUE，Exchange Server 會使用此屬性在 Outlook 全域通訊清單 (GAL) 隱藏該連絡人。</span><span class="sxs-lookup"><span data-stu-id="b17a1-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="b17a1-256">同樣地，如果此屬性的值是 TRUE，[使用者複寫器] 不會在 AbUserEntry 資料表中加入該使用者，而此使用者不會出現在 Address Book Server 檔案中。</span><span class="sxs-lookup"><span data-stu-id="b17a1-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="b17a1-p120">您可以使用一些旗標位元來定義要在 Address Book Server 屬性上使用的篩選器。例如，某些旗標位元的存在可將屬性識別為包含屬性或排除屬性。[使用者複寫器] 會濾除含有排除屬性的連絡人，並濾除不含包含屬性的連絡人。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b17a1-260">如需篩選通訊錄的詳細資訊，請參閱<A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Lync Server 2013 中的 Address Book Server cmdlet</A>，並<A href="https://go.microsoft.com/fwlink/?linkid=330430">篩選 Lync 2013 通訊錄</A></span><span class="sxs-lookup"><span data-stu-id="b17a1-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="b17a1-p121">目前，有三種不同的篩選器。下表列出這些篩選器。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b17a1-263">屬性</span><span class="sxs-lookup"><span data-stu-id="b17a1-263">Attribute</span></span></th>
<th><span data-ttu-id="b17a1-264">描述</span><span class="sxs-lookup"><span data-stu-id="b17a1-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-265">0x800</span><span class="sxs-lookup"><span data-stu-id="b17a1-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p122">如果設定，則這將識別連絡人的必要屬性。[使用者複寫器] 會使用此旗標位元來濾除不含至少一個必要屬性的連絡人。OuPathId 是一律會設定的必要屬性。因此，至少應該再設定另一個必要屬性。否則，仍然不會將連絡人 (具有必要屬性 OuPathId 的值) 寫入資料庫。例如，如果 <strong>telephoneNumber</strong> 和 <strong>homePhone</strong> 是定義為必要屬性，則只會將具有至少其中一個屬性的連絡人寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b17a1-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="b17a1-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p123">如果設定，則這將識別排除屬性。[使用者複寫器] 會使用此旗標位元來濾除包含此屬性的連絡人。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 是定義為排除屬性，則不會將具有此屬性的連絡人寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b17a1-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="b17a1-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="b17a1-p124">如果設定，則這將識別包含屬性。[使用者複寫器] 會使用此旗標位元來濾除不含此屬性的連絡人。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 是定義為包含屬性，則只會將具有此屬性的連絡人寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b17a1-280">如果同時設定 0x4000 (排除屬性) 和 0x8000 (包含屬性) 旗標位元，則 0x4000 位元會覆寫 0x8000 位元，並排除該連絡人。</span><span class="sxs-lookup"><span data-stu-id="b17a1-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="b17a1-p125">雖然您可以篩選通訊錄來僅包含某些使用者，但限制項目並不會限制其他使用者連絡被濾除的使用者，或查看其顯示狀態的能力。使用者一律可以輸入使用者的完整登入名稱，以尋找不在通訊錄中的使用者，或是對其手動傳送即時訊息或手動進行呼叫。另外，在 Outlook 中也可以找到使用者的連絡資訊。</span><span class="sxs-lookup"><span data-stu-id="b17a1-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="b17a1-284">Address Book 檔案中具有完整連絡人記錄可讓您使用 Lync Server，啟動電子郵件，而電話或 Enterprise Voice 通話 （亦即，如果在伺服器上啟用 Enterprise Voice） 與未設定的工作階段初始的使用者通訊協定 (SIP)，有些組織想要在其 Address Book Server 項目中包含只有已啟用 SIP 的使用者。</span><span class="sxs-lookup"><span data-stu-id="b17a1-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="b17a1-285">您可以篩選通訊錄若要清除 0x800 位元**旗標**] 欄中的下列必要的屬性包含只有已啟用 SIP 的使用者： **mailNickname**、 **telephoneNumber**、**住家電話**，以及**行動裝置**。</span><span class="sxs-lookup"><span data-stu-id="b17a1-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="b17a1-286">您也可以篩選通訊錄加入只有已啟用 SIP 的使用者藉由設定 0x8000 （包含屬性） 的**Msrtcsip-primaryuseraddress**屬性的**旗標**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="b17a1-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="b17a1-287">這也有助於排除通訊錄檔案的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="b17a1-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="b17a1-288">修改 AbAttribute 資料表之後，您可以執行 Cmdlet **Update-CsUserDatabase** 命令，以重新整理 AbUserEntry 資料表中的資料。</span><span class="sxs-lookup"><span data-stu-id="b17a1-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="b17a1-289">在 UR 複寫完成之後，您可以手動執行 Cmdlet **UpdateCsAddressBook** 命令，以更新 Address Book Server 檔案存放區中的檔案。</span><span class="sxs-lookup"><span data-stu-id="b17a1-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b17a1-290">前端伺服器所在 Address Book Server 不行政規定必須加以設定。</span><span class="sxs-lookup"><span data-stu-id="b17a1-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="b17a1-291">其中一個會選擇在部署期間，通常是第一個前端伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="b17a1-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="b17a1-292">發生失敗，通訊錄服務將會移到另一個前端伺服器，並請注意您沒有系統管理。</span><span class="sxs-lookup"><span data-stu-id="b17a1-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b17a1-293">如果您有合併或修改您從多重樹系部署或 （例如移至 Lync Server 之前合併您的基礎結構） 的父系/子系部署的基礎結構，您可能會發現部分使用者下載通訊錄服務和通訊錄 Web 查詢失敗。</span><span class="sxs-lookup"><span data-stu-id="b17a1-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="b17a1-294">在具有多個網域或樹系的部署中，出現此問題的使用者物件上已填入屬性 <STRONG>MsRTCSIP-OriginatorSid</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="b17a1-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="b17a1-295">您必須將這些物件的 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 屬性設為 NULL，才能解決此問題。</span><span class="sxs-lookup"><span data-stu-id="b17a1-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

