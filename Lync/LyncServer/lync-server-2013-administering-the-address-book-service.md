---
title: Lync Server 2013：管理通訊錄服務
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
ms.openlocfilehash: 7a5f7a6a30e510bdcdb57d9f8a2f5a15fe8a7f37
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521190"
---
# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="4df3c-102">在 Lync Server 2013 中管理通訊錄服務</span><span class="sxs-lookup"><span data-stu-id="4df3c-102">Administering the Address Book Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4df3c-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="4df3c-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="4df3c-104">在 Lync Server、Enterprise Edition 或 Standard Edition Server 的部署中，預設會安裝通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="4df3c-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="4df3c-105">Address Book Service 所使用的資料庫– RTCab –會建立在 Enterprise Edition 的 SQL Server (上，這是後端 SQL Server;對於 Standard Edition server，組合 SQL Server) 。</span><span class="sxs-lookup"><span data-stu-id="4df3c-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4df3c-106">如需使用 <STRONG>adsi</STRONG> 編輯器編輯 Active Directory 網域服務物件屬性的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI 編輯器</A>。</span><span class="sxs-lookup"><span data-stu-id="4df3c-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="4df3c-107">如需資源工具組中專用於通訊錄服務之工具的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource 工具組工具</A>。</span><span class="sxs-lookup"><span data-stu-id="4df3c-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="4df3c-108">Address Book Server 電話號碼正規化</span><span class="sxs-lookup"><span data-stu-id="4df3c-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="4df3c-109">Lync Server 需要標準化的 RFC 3966/e.164 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4df3c-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="4df3c-110">若要使用未結構化或格式不正確的電話號碼，Lync Server 會依靠通訊錄服務器來預處理電話號碼，然後再將其傳遞給正規化規則。</span><span class="sxs-lookup"><span data-stu-id="4df3c-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="4df3c-111">當您從通訊錄使用電話號碼，且套用正常化規則時，用戶端（例如 Lync Phone Edition 和 Lync Mobile）可以使用這些正規化的數位。</span><span class="sxs-lookup"><span data-stu-id="4df3c-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="4df3c-p104">舊版中使用的正規化規則可能需要經過一些調整才能正常使用。因為在交給正規化規則之前會先移除空格和非強制字元，所以如果 regex 運算式明確尋找虛線或其他已移除的字元，正規化規則可能會失敗。您應該檢閱正規化規則，確保它們不會尋找這類非強制字元，否則，如果規則預期字元存在而字元不存在，規則就會先按正常程序失敗再繼續運作。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="4df3c-115">使用者複寫器和 Address Book Server</span><span class="sxs-lookup"><span data-stu-id="4df3c-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="4df3c-116">Address Book Server 會使用 [使用者複寫器] 提供的資料，來更新其最初從全域通訊清單 (GAL) 取得的資訊。</span><span class="sxs-lookup"><span data-stu-id="4df3c-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="4df3c-117">使用者複寫器會將每個使用者、連絡人及群組的 Active Directory 網域服務屬性寫入資料庫中的 AbUserEntry 資料表，而通訊錄服務器會將資料庫中的使用者資料同步處理至通訊錄服務器檔案存放區中的檔案和通訊錄資料庫 RTCab。</span><span class="sxs-lookup"><span data-stu-id="4df3c-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="4df3c-118">AbUserEntry 資料表的架構使用兩個資料行 **UserGuid** 和 **UserData**。</span><span class="sxs-lookup"><span data-stu-id="4df3c-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="4df3c-119">**UserGuid** 是索引欄，包含 Active Directory 物件的16位元組 GUID。</span><span class="sxs-lookup"><span data-stu-id="4df3c-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="4df3c-120">**UserData** 是一個影像欄，其中包含所有先前提及的該連絡人的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="4df3c-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="4df3c-121">使用者複寫器會透過讀取位於相同 SQL Server 型實例中的設定資料表，以 AbUserEntry 表格，判斷要寫入哪些 Active Directory 屬性。</span><span class="sxs-lookup"><span data-stu-id="4df3c-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="4df3c-122">AbAttribute 資料表包含三個資料行 **ID**、**Name**、**Flags** 和 **Enable**。</span><span class="sxs-lookup"><span data-stu-id="4df3c-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="4df3c-123">此資料表是在資料庫設定期間建立。</span><span class="sxs-lookup"><span data-stu-id="4df3c-123">The table is created during database setup.</span></span> <span data-ttu-id="4df3c-124">如果 AbAttribute 資料表是空的，[使用者複寫器] 會略過其 AbUserEntry 資料表處理邏輯。</span><span class="sxs-lookup"><span data-stu-id="4df3c-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="4df3c-125">Address Book Server 屬性是從 AbAttribute 資料表擷取的動態屬性，該資料表最初是在 Address Book Server 啟動時由 Address Book Server 寫入。</span><span class="sxs-lookup"><span data-stu-id="4df3c-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="4df3c-126">Address Book Server 啟用會以下表所示的值填入 AbAttribute 表格。</span><span class="sxs-lookup"><span data-stu-id="4df3c-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4df3c-127">識別碼</span><span class="sxs-lookup"><span data-stu-id="4df3c-127">ID</span></span></th>
<th><span data-ttu-id="4df3c-128">名稱</span><span class="sxs-lookup"><span data-stu-id="4df3c-128">Name</span></span></th>
<th><span data-ttu-id="4df3c-129">Flags</span><span class="sxs-lookup"><span data-stu-id="4df3c-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-130">1 </span><span class="sxs-lookup"><span data-stu-id="4df3c-130">1</span></span></p></td>
<td><p><span data-ttu-id="4df3c-131">givenName</span><span class="sxs-lookup"><span data-stu-id="4df3c-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="4df3c-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="4df3c-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-133">第</span><span class="sxs-lookup"><span data-stu-id="4df3c-133">2</span></span></p></td>
<td><p><span data-ttu-id="4df3c-134">錫</span><span class="sxs-lookup"><span data-stu-id="4df3c-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="4df3c-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="4df3c-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-136">個</span><span class="sxs-lookup"><span data-stu-id="4df3c-136">3</span></span></p></td>
<td><p><span data-ttu-id="4df3c-137">displayName</span><span class="sxs-lookup"><span data-stu-id="4df3c-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="4df3c-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="4df3c-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-139">4 </span><span class="sxs-lookup"><span data-stu-id="4df3c-139">4</span></span></p></td>
<td><p><span data-ttu-id="4df3c-140">標題</span><span class="sxs-lookup"><span data-stu-id="4df3c-140">Title</span></span></p></td>
<td><p><span data-ttu-id="4df3c-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="4df3c-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-142">5 </span><span class="sxs-lookup"><span data-stu-id="4df3c-142">5</span></span></p></td>
<td><p><span data-ttu-id="4df3c-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="4df3c-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="4df3c-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="4df3c-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-145">6 </span><span class="sxs-lookup"><span data-stu-id="4df3c-145">6</span></span></p></td>
<td><p><span data-ttu-id="4df3c-146">Company</span><span class="sxs-lookup"><span data-stu-id="4df3c-146">Company</span></span></p></td>
<td><p><span data-ttu-id="4df3c-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="4df3c-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-148">7 </span><span class="sxs-lookup"><span data-stu-id="4df3c-148">7</span></span></p></td>
<td><p><span data-ttu-id="4df3c-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="4df3c-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="4df3c-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="4df3c-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-151">8 </span><span class="sxs-lookup"><span data-stu-id="4df3c-151">8</span></span></p></td>
<td><p><span data-ttu-id="4df3c-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="4df3c-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="4df3c-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="4df3c-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-154">9 </span><span class="sxs-lookup"><span data-stu-id="4df3c-154">9</span></span></p></td>
<td><p><span data-ttu-id="4df3c-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="4df3c-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="4df3c-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="4df3c-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-157">10 </span><span class="sxs-lookup"><span data-stu-id="4df3c-157">10</span></span></p></td>
<td><p><span data-ttu-id="4df3c-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="4df3c-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="4df3c-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="4df3c-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-160">11 </span><span class="sxs-lookup"><span data-stu-id="4df3c-160">11</span></span></p></td>
<td><p><span data-ttu-id="4df3c-161">Mobile</span><span class="sxs-lookup"><span data-stu-id="4df3c-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="4df3c-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="4df3c-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-163">12 </span><span class="sxs-lookup"><span data-stu-id="4df3c-163">12</span></span></p></td>
<td><p><span data-ttu-id="4df3c-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="4df3c-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="4df3c-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="4df3c-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-166">13 </span><span class="sxs-lookup"><span data-stu-id="4df3c-166">13</span></span></p></td>
<td><p><span data-ttu-id="4df3c-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="4df3c-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="4df3c-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="4df3c-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-169">14 </span><span class="sxs-lookup"><span data-stu-id="4df3c-169">14</span></span></p></td>
<td><p><span data-ttu-id="4df3c-170">郵件</span><span class="sxs-lookup"><span data-stu-id="4df3c-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="4df3c-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="4df3c-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-172">15 </span><span class="sxs-lookup"><span data-stu-id="4df3c-172">15</span></span></p></td>
<td><p><span data-ttu-id="4df3c-173">groupType</span><span class="sxs-lookup"><span data-stu-id="4df3c-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="4df3c-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="4df3c-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-175">16 </span><span class="sxs-lookup"><span data-stu-id="4df3c-175">16</span></span></p></td>
<td><p><span data-ttu-id="4df3c-176">部門</span><span class="sxs-lookup"><span data-stu-id="4df3c-176">Department</span></span></p></td>
<td><p><span data-ttu-id="4df3c-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="4df3c-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-178">17 </span><span class="sxs-lookup"><span data-stu-id="4df3c-178">17</span></span></p></td>
<td><p><span data-ttu-id="4df3c-179">描述</span><span class="sxs-lookup"><span data-stu-id="4df3c-179">Description</span></span></p></td>
<td><p><span data-ttu-id="4df3c-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="4df3c-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-181">18 </span><span class="sxs-lookup"><span data-stu-id="4df3c-181">18</span></span></p></td>
<td><p><span data-ttu-id="4df3c-182">管理員</span><span class="sxs-lookup"><span data-stu-id="4df3c-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="4df3c-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="4df3c-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-184">19</span><span class="sxs-lookup"><span data-stu-id="4df3c-184">19</span></span></p></td>
<td><p><span data-ttu-id="4df3c-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="4df3c-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="4df3c-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="4df3c-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-187">共</span><span class="sxs-lookup"><span data-stu-id="4df3c-187">20</span></span></p></td>
<td><p><span data-ttu-id="4df3c-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="4df3c-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="4df3c-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="4df3c-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-190">99</span><span class="sxs-lookup"><span data-stu-id="4df3c-190">99</span></span></p></td>
<td><p><span data-ttu-id="4df3c-191">條目</span><span class="sxs-lookup"><span data-stu-id="4df3c-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="4df3c-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="4df3c-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4df3c-193">**ID** 資料行中的數字必須是唯一的，且絕不可重複使用。</span><span class="sxs-lookup"><span data-stu-id="4df3c-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="4df3c-194">另外，保持 ID 值小於 256 可在 Address Book Server 寫入的輸出檔中節省空間。</span><span class="sxs-lookup"><span data-stu-id="4df3c-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="4df3c-195">不過，ID 最大值是 65535。</span><span class="sxs-lookup"><span data-stu-id="4df3c-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="4df3c-196">[ **名稱** ] 欄會對應至使用者複寫器應該放置於每個連絡人的 AbUserEntry 表格中的 Active Directory 屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="4df3c-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="4df3c-197">**Flags** 資料行中的值用來定義屬性的類型。</span><span class="sxs-lookup"><span data-stu-id="4df3c-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="4df3c-198">[使用者複寫器] 認得下列類型的 Address Book Server 屬性 (以 **Flags** 資料行中的值的低位元組表示)。</span><span class="sxs-lookup"><span data-stu-id="4df3c-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4df3c-199">屬性</span><span class="sxs-lookup"><span data-stu-id="4df3c-199">Attribute</span></span></th>
<th><span data-ttu-id="4df3c-200">描述</span><span class="sxs-lookup"><span data-stu-id="4df3c-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-201">0x0</span><span class="sxs-lookup"><span data-stu-id="4df3c-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p108">字串屬性。[使用者複寫器] 會先將此類型轉換為 UTF-8，再將之儲存於 AbUserEntry 資料表。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-204">0x1</span><span class="sxs-lookup"><span data-stu-id="4df3c-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p109">二進位屬性。[使用者複寫器] 會以二進位大型物件儲存此屬性而不做任何轉換。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-207">求</span><span class="sxs-lookup"><span data-stu-id="4df3c-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="4df3c-208">String 屬性，但只有在屬性值以電話開頭時，才會包含此屬性 &quot; ： &quot; 。</span><span class="sxs-lookup"><span data-stu-id="4df3c-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="4df3c-209">這主要用於多重值字串屬性，特別是 <strong>proxyAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="4df3c-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="4df3c-210">在此情況下，Address Book Server 只會對以電話開始的 <strong>proxyAddresses</strong> 專案感興趣 &quot; ： &quot; 。</span><span class="sxs-lookup"><span data-stu-id="4df3c-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="4df3c-211">因此，由於節省空間，使用者複寫器只會儲存以 &quot; 電話：的專案 &quot; 。</span><span class="sxs-lookup"><span data-stu-id="4df3c-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-212">0x3</span><span class="sxs-lookup"><span data-stu-id="4df3c-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p111">布林字串屬性，TRUE 會使 [使用者複寫器] 不將此連絡人放入 AbUserEntry 資料表中。如果是 FALSE，則會使 [使用者複寫器] 將此連絡人的屬性放入 AbUserEntry 資料表中，但不包括具有此旗標的特定屬性。這是另一個主要用於 <strong>msExchHideFromAddressLists</strong> 屬性的特殊案例類型。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-216">0x4</span><span class="sxs-lookup"><span data-stu-id="4df3c-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="4df3c-217">String 屬性，但只有在屬性值以 smtp 開頭時，才會包含 &quot; 此屬性： &quot; 並包含 &quot; @ &quot; 符號。</span><span class="sxs-lookup"><span data-stu-id="4df3c-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-218">0x5</span><span class="sxs-lookup"><span data-stu-id="4df3c-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="4df3c-219">String 屬性，但只有在屬性值開頭為 &quot; 電話： &quot; 或 &quot; smtp： &quot; 並包含 &quot; @ &quot; 符號時，才會包含此屬性。</span><span class="sxs-lookup"><span data-stu-id="4df3c-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-220">0x100</span><span class="sxs-lookup"><span data-stu-id="4df3c-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="4df3c-221">如果設定，則這是可針對每個連絡人出現一次以上的多重值屬性。</span><span class="sxs-lookup"><span data-stu-id="4df3c-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-222">0x400</span><span class="sxs-lookup"><span data-stu-id="4df3c-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p112">如果設定，則這將識別連絡人的電子郵件使用者帳戶名稱屬性。Address Book Server 會使用此旗標來識別要在電話正規化事件記錄項目中顯示的屬性值。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-225">0x800</span><span class="sxs-lookup"><span data-stu-id="4df3c-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p113">如果設定，則這將識別連絡人的必要屬性。只有當此屬性在 Active Directory 中有值時，Address Book Server 才會在 AbUserEntry 資料表中加入使用者。如果有一個以上的必要屬性，則只要其中一個有值，就會在 AbUserEntry 資料表中加入使用者。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="4df3c-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="4df3c-230">如果設定，則 Address Book Server 一律會正規化此屬性的值。</span><span class="sxs-lookup"><span data-stu-id="4df3c-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="4df3c-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="4df3c-232">如果設定，則當 <strong>UseNormalizationRules</strong> CMS 設定為 FALSE 時，Address Book Server 會使用 <strong>proxyAddresses</strong> 中的正規化數字，否則其行為與旗標位元為 0x1000 時相同。</span><span class="sxs-lookup"><span data-stu-id="4df3c-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="4df3c-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p114">如果設定，則 Address Book Server 不會在 AbUserEntry 資料表中加入所指定的屬性為此值的物件。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 屬性已設定此旗標位元，則不會將具有此屬性的連絡人寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="4df3c-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p115">如果設定，則 Address Book Server 不會將所指定的屬性不是此值的物件加入 AbUserEntry 資料表。如果物件上同時設定 0x4000 和 0x8000 旗標位元，則以旗標位元值設為 0x4000 的屬性為優先，且會從 AbUserEntry 資料表中排除物件。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="4df3c-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p116">如果設定，則這代表群組物件。[使用者複寫器] 會使用此旗標位元來加入具有 <strong>groupType</strong> 屬性 (表示這是群組) 的連絡人，例如，通訊群組清單或安全性群組。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="4df3c-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="4df3c-243">如果設定，則 [使用者複寫器] 會使用此旗標位元將此屬性加入裝置特定 Address Book Server 檔案 (副檔名為 .dabs 的檔案)。</span><span class="sxs-lookup"><span data-stu-id="4df3c-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4df3c-244">在舊版的 Lync Server 中，將變更套用至 Active Directory 時，系統管理員必須執行 **CSUserDatabase** 和 **update-update-csaddressbook** Windows PowerShell Cmdlet，以將變更立即保存至 Lync Server 使用者資料庫及 RTCab 資料庫。</span><span class="sxs-lookup"><span data-stu-id="4df3c-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="4df3c-245">在 Lync Server 2013 中，Lync Server 使用者複寫器會從 Active Directory 中挑選變更，並根據設定的間隔來更新 Lync Server 使用者資料庫。</span><span class="sxs-lookup"><span data-stu-id="4df3c-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="4df3c-246">Lync Server 使用者複寫器也會快速傳播變更至 RTCab 資料庫，而不需管理員必須執行 Update-csaddressbook 的更新。</span><span class="sxs-lookup"><span data-stu-id="4df3c-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="4df3c-247">如果啟用通訊錄 Web 查詢，則變更將會反映在 Lync 用戶端的搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="4df3c-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="4df3c-248">只有在啟用通訊錄檔案下載時，系統管理員才需要執行 Update-csaddressbook 更新。</span><span class="sxs-lookup"><span data-stu-id="4df3c-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4df3c-249">依預設，Lync Server 使用者複寫器每5分鐘自動執行一次。</span><span class="sxs-lookup"><span data-stu-id="4df3c-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="4df3c-250">您可以使用 CSUserReplicatorConfiguration-ReplicationCycleInterval 來設定此間隔 &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="4df3c-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="4df3c-251">篩選通訊錄</span><span class="sxs-lookup"><span data-stu-id="4df3c-251">Filtering the Address Book</span></span>

<span data-ttu-id="4df3c-252">在通訊錄服務器檔案中填入的使用者，可根據 AbAttribute 表格中所列的特定 Active Directory 網域服務屬性進行控制。</span><span class="sxs-lookup"><span data-stu-id="4df3c-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="4df3c-253">其中一個這類可用於篩選的屬性就是 **msExchangeHideFromAddressBook** 屬性。</span><span class="sxs-lookup"><span data-stu-id="4df3c-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="4df3c-254">這是由 Exchange 架構所新增的使用者屬性。</span><span class="sxs-lookup"><span data-stu-id="4df3c-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="4df3c-255">如果此屬性的值是 TRUE，Exchange Server 會使用此屬性在 Outlook 全域通訊清單 (GAL) 隱藏該連絡人。</span><span class="sxs-lookup"><span data-stu-id="4df3c-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="4df3c-256">同樣地，如果此屬性的值是 TRUE，[使用者複寫器] 不會在 AbUserEntry 資料表中加入該使用者，而此使用者不會出現在 Address Book Server 檔案中。</span><span class="sxs-lookup"><span data-stu-id="4df3c-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="4df3c-p120">您可以使用一些旗標位元來定義要在 Address Book Server 屬性上使用的篩選器。例如，某些旗標位元的存在可將屬性識別為包含屬性或排除屬性。[使用者複寫器] 會濾除含有排除屬性的連絡人，並濾除不含包含屬性的連絡人。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4df3c-260">如需篩選通訊錄的詳細資訊，請參閱 <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Lync server 2013 中的通訊錄服務器 Cmdlet</A>及 <A href="https://go.microsoft.com/fwlink/?linkid=330430">篩選 Lync 2013 通訊錄</A></span><span class="sxs-lookup"><span data-stu-id="4df3c-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="4df3c-p121">目前，有三種不同的篩選器。下表列出這些篩選器。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4df3c-263">屬性</span><span class="sxs-lookup"><span data-stu-id="4df3c-263">Attribute</span></span></th>
<th><span data-ttu-id="4df3c-264">描述</span><span class="sxs-lookup"><span data-stu-id="4df3c-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-265">0x800</span><span class="sxs-lookup"><span data-stu-id="4df3c-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p122">如果設定，則這將識別連絡人的必要屬性。[使用者複寫器] 會使用此旗標位元來濾除不含至少一個必要屬性的連絡人。OuPathId 是一律會設定的必要屬性。因此，至少應該再設定另一個必要屬性。否則，仍然不會將連絡人 (具有必要屬性 OuPathId 的值) 寫入資料庫。例如，如果 <strong>telephoneNumber</strong> 和 <strong>homePhone</strong> 是定義為必要屬性，則只會將具有至少其中一個屬性的連絡人寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4df3c-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="4df3c-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p123">如果設定，則這將識別排除屬性。[使用者複寫器] 會使用此旗標位元來濾除包含此屬性的連絡人。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 是定義為排除屬性，則不會將具有此屬性的連絡人寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4df3c-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="4df3c-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="4df3c-p124">如果設定，則這將識別包含屬性。[使用者複寫器] 會使用此旗標位元來濾除不含此屬性的連絡人。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 是定義為包含屬性，則只會將具有此屬性的連絡人寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="4df3c-280">如果同時設定 0x4000 (排除屬性) 和 0x8000 (包含屬性) 旗標位元，則 0x4000 位元會覆寫 0x8000 位元，並排除該連絡人。</span><span class="sxs-lookup"><span data-stu-id="4df3c-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="4df3c-p125">雖然您可以篩選通訊錄來僅包含某些使用者，但限制項目並不會限制其他使用者連絡被濾除的使用者，或查看其顯示狀態的能力。使用者一律可以輸入使用者的完整登入名稱，以尋找不在通訊錄中的使用者，或是對其手動傳送即時訊息或手動進行呼叫。另外，在 Outlook 中也可以找到使用者的連絡資訊。</span><span class="sxs-lookup"><span data-stu-id="4df3c-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="4df3c-284">在通訊錄檔案中有完整的連絡人記錄可讓您使用 Lync Server 來發起電子郵件、電話或企業語音通話 (也就是說，如果) 伺服器上已啟用 Enterprise Voice，且使用者未設定會話初始通訊協定 (SIP) 的使用者，則某些組織喜歡在其通訊錄服務器專案中只包含 SIP-enabled 的使用者。</span><span class="sxs-lookup"><span data-stu-id="4df3c-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="4df3c-285">您可以在下列必要屬性（ **mailNickname**、 **telephoneNumber**、 **homePhone\*\*\*\*及行動**裝置）的 [**旗標**] 欄中清除0x800 位，以篩選通訊錄以只包含 SIP-enabled 使用者。</span><span class="sxs-lookup"><span data-stu-id="4df3c-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="4df3c-286">您也可以在**msRTCSIP-PrimaryUserAddress**屬性的 [**旗標**] 欄中，設定 0x8000 (include 屬性) ，以篩選通訊錄僅包括 SIP-enabled 使用者。</span><span class="sxs-lookup"><span data-stu-id="4df3c-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="4df3c-287">這也有助於從通訊錄檔案中排除服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="4df3c-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="4df3c-288">修改 AbAttribute 資料表之後，您可以執行 Cmdlet **Update-CsUserDatabase** 命令，以重新整理 AbUserEntry 資料表中的資料。</span><span class="sxs-lookup"><span data-stu-id="4df3c-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="4df3c-289">在 UR 複寫完成之後，您可以手動執行 Cmdlet **UpdateCsAddressBook** 命令，以更新 Address Book Server 檔案存放區中的檔案。</span><span class="sxs-lookup"><span data-stu-id="4df3c-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4df3c-290">通訊錄服務器所放置的前端伺服器並不是可管理的。</span><span class="sxs-lookup"><span data-stu-id="4df3c-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="4df3c-291">部署期間會選擇一個，通常是第一部前端伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="4df3c-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="4df3c-292">發生失敗時，通訊錄服務會移至另一部前端伺服器，不需要系統管理的注意力。</span><span class="sxs-lookup"><span data-stu-id="4df3c-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4df3c-293">如果您已從多樹系部署或父/子部署中合併或修改基礎結構，則 (例如先合併基礎結構，再移至 Lync Server) ，您可能會發現某些使用者的通訊錄服務下載和通訊錄 Web 查詢失敗。</span><span class="sxs-lookup"><span data-stu-id="4df3c-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="4df3c-294">在具有多個網域或樹系的部署中，出現此問題的使用者物件上已填入屬性 <STRONG>MsRTCSIP-OriginatorSid</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="4df3c-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="4df3c-295">您必須將這些物件的 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 屬性設為 NULL，才能解決此問題。</span><span class="sxs-lookup"><span data-stu-id="4df3c-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

