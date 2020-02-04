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
ms.openlocfilehash: 5d12b904cbb679b66579c7c669ba46e0d732034b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="2152f-102">在 Lync Server 2013 中管理通訊錄服務</span><span class="sxs-lookup"><span data-stu-id="2152f-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2152f-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="2152f-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="2152f-104">在 Lync Server、Enterprise Edition 或 Standard Edition Server 的部署中，預設會安裝通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="2152f-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="2152f-105">通訊錄服務所使用的資料庫– RTCab –是在 SQL Server 上建立（適用于企業版），這是後端 SQL Server; 針對標準版伺服器，則是 collocated SQL Server）。</span><span class="sxs-lookup"><span data-stu-id="2152f-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2152f-106">如需使用<STRONG>Adsi 編輯</STRONG>來編輯 Active Directory 網域服務物件屬性的詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI 編輯</A>。</span><span class="sxs-lookup"><span data-stu-id="2152f-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="2152f-107">如需有關專門用於通訊錄服務之資源套件中之工具的詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 資源套件工具</A>。</span><span class="sxs-lookup"><span data-stu-id="2152f-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="2152f-108">通訊錄服務器電話號碼正規化</span><span class="sxs-lookup"><span data-stu-id="2152f-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="2152f-109">Lync Server 需要標準化的 RFC 3966/E. 164 個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2152f-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="2152f-110">若要使用非結構化或格式不一致的電話號碼，Lync Server 依賴通訊錄服務器來預處理電話號碼，然後再將其移交給正常化規則。</span><span class="sxs-lookup"><span data-stu-id="2152f-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="2152f-111">在通訊錄中使用電話號碼並套用正常化規則時，用戶端（例如 Lync 手機版和 Lync Mobile）都可以使用這些標準化的數位。</span><span class="sxs-lookup"><span data-stu-id="2152f-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="2152f-112">在舊版中使用的正常化規則可能無法正常運作，無需進行一些調整。</span><span class="sxs-lookup"><span data-stu-id="2152f-112">The normalization rules that were used in previous versions may not work properly without some adjustments.</span></span> <span data-ttu-id="2152f-113">因為將在正常化規則之前移除空白和非強制字元，所以如果您的 RegEx 運算式特別尋找的是虛線或其他已移除的字元，您的正常化規則可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="2152f-113">Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail.</span></span> <span data-ttu-id="2152f-114">您應該檢查您的正常化規則，以確保它們無法尋找這些非強制字元，或規則可能會順利失敗，並在規則預期會出現時，繼續執行該字元。</span><span class="sxs-lookup"><span data-stu-id="2152f-114">You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="2152f-115">使用者複製程式和通訊錄服務器</span><span class="sxs-lookup"><span data-stu-id="2152f-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="2152f-116">通訊錄服務器會使用使用者複製器提供的資料，來更新它最初從全域通訊清單（GAL）中獲得的資訊。</span><span class="sxs-lookup"><span data-stu-id="2152f-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="2152f-117">使用者複製程式會將每個使用者、連絡人和群組的 Active Directory 網域服務屬性寫入資料庫中的 AbUserEntry 資料表，而通訊錄服務器會將資料庫中的使用者資料同步處理到通訊錄服務器檔存放區中的檔案，並到通訊錄資料庫 RTCab。</span><span class="sxs-lookup"><span data-stu-id="2152f-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="2152f-118">AbUserEntry 資料表的架構使用兩個數據行， **UserGuid**與**UserData**。</span><span class="sxs-lookup"><span data-stu-id="2152f-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="2152f-119">**UserGuid**是 [索引] 資料行，包含 Active Directory 物件的16個位元組 GUID。</span><span class="sxs-lookup"><span data-stu-id="2152f-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="2152f-120">**UserData**是一個 image 欄，其中包含該連絡人所有先前提及的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="2152f-121">使用者複製程式會透過讀取位於同一 SQL Server 型實例中的設定資料表，以 AbUserEntry 資料表來決定要寫入哪些 Active Directory 屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="2152f-122">AbAttribute 資料表包含三個數據行、**識別碼**、**名稱**、**標記**，以及**Enable**。</span><span class="sxs-lookup"><span data-stu-id="2152f-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="2152f-123">資料表是在建立資料庫期間建立的。</span><span class="sxs-lookup"><span data-stu-id="2152f-123">The table is created during database setup.</span></span> <span data-ttu-id="2152f-124">如果 AbAttribute 資料表是空的，使用者複製程式會跳過其 AbUserEntry table 處理邏輯。</span><span class="sxs-lookup"><span data-stu-id="2152f-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="2152f-125">[通訊錄服務器] 屬性是動態的，而且是從 AbAttribute 資料表中檢索，在通訊錄服務器啟動時，由通訊錄服務器最初撰寫。</span><span class="sxs-lookup"><span data-stu-id="2152f-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="2152f-126">通訊錄服務器啟用會以下表中顯示的值來填入 AbAttribute 資料表。</span><span class="sxs-lookup"><span data-stu-id="2152f-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2152f-127">標識號</span><span class="sxs-lookup"><span data-stu-id="2152f-127">ID</span></span></th>
<th><span data-ttu-id="2152f-128">名稱</span><span class="sxs-lookup"><span data-stu-id="2152f-128">Name</span></span></th>
<th><span data-ttu-id="2152f-129">筆記</span><span class="sxs-lookup"><span data-stu-id="2152f-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2152f-130">1</span><span class="sxs-lookup"><span data-stu-id="2152f-130">1</span></span></p></td>
<td><p><span data-ttu-id="2152f-131">givenName</span><span class="sxs-lookup"><span data-stu-id="2152f-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="2152f-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="2152f-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-133">2</span><span class="sxs-lookup"><span data-stu-id="2152f-133">2</span></span></p></td>
<td><p><span data-ttu-id="2152f-134">Sn.exe</span><span class="sxs-lookup"><span data-stu-id="2152f-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="2152f-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="2152f-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-136">3</span><span class="sxs-lookup"><span data-stu-id="2152f-136">3</span></span></p></td>
<td><p><span data-ttu-id="2152f-137">displayName</span><span class="sxs-lookup"><span data-stu-id="2152f-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="2152f-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="2152f-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-139">4</span><span class="sxs-lookup"><span data-stu-id="2152f-139">4</span></span></p></td>
<td><p><span data-ttu-id="2152f-140">職稱</span><span class="sxs-lookup"><span data-stu-id="2152f-140">Title</span></span></p></td>
<td><p><span data-ttu-id="2152f-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="2152f-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-142">500</span><span class="sxs-lookup"><span data-stu-id="2152f-142">5</span></span></p></td>
<td><p><span data-ttu-id="2152f-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="2152f-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="2152f-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="2152f-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-145">6</span><span class="sxs-lookup"><span data-stu-id="2152f-145">6</span></span></p></td>
<td><p><span data-ttu-id="2152f-146">家</span><span class="sxs-lookup"><span data-stu-id="2152f-146">Company</span></span></p></td>
<td><p><span data-ttu-id="2152f-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="2152f-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-148">utf-7</span><span class="sxs-lookup"><span data-stu-id="2152f-148">7</span></span></p></td>
<td><p><span data-ttu-id="2152f-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="2152f-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="2152f-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="2152f-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-151">型</span><span class="sxs-lookup"><span data-stu-id="2152f-151">8</span></span></p></td>
<td><p><span data-ttu-id="2152f-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="2152f-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="2152f-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="2152f-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-154">9</span><span class="sxs-lookup"><span data-stu-id="2152f-154">9</span></span></p></td>
<td><p><span data-ttu-id="2152f-155">Telephonenumber 相同</span><span class="sxs-lookup"><span data-stu-id="2152f-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="2152f-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="2152f-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-157">第</span><span class="sxs-lookup"><span data-stu-id="2152f-157">10</span></span></p></td>
<td><p><span data-ttu-id="2152f-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="2152f-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="2152f-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="2152f-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-160">11</span><span class="sxs-lookup"><span data-stu-id="2152f-160">11</span></span></p></td>
<td><p><span data-ttu-id="2152f-161">行動裝置</span><span class="sxs-lookup"><span data-stu-id="2152f-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="2152f-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="2152f-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-163">之間</span><span class="sxs-lookup"><span data-stu-id="2152f-163">12</span></span></p></td>
<td><p><span data-ttu-id="2152f-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="2152f-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="2152f-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="2152f-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-166">合</span><span class="sxs-lookup"><span data-stu-id="2152f-166">13</span></span></p></td>
<td><p><span data-ttu-id="2152f-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="2152f-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="2152f-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="2152f-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-169">4</span><span class="sxs-lookup"><span data-stu-id="2152f-169">14</span></span></p></td>
<td><p><span data-ttu-id="2152f-170">郵遞</span><span class="sxs-lookup"><span data-stu-id="2152f-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="2152f-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="2152f-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-172">工資</span><span class="sxs-lookup"><span data-stu-id="2152f-172">15</span></span></p></td>
<td><p><span data-ttu-id="2152f-173">groupType</span><span class="sxs-lookup"><span data-stu-id="2152f-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="2152f-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="2152f-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-175">位</span><span class="sxs-lookup"><span data-stu-id="2152f-175">16</span></span></p></td>
<td><p><span data-ttu-id="2152f-176">部門</span><span class="sxs-lookup"><span data-stu-id="2152f-176">Department</span></span></p></td>
<td><p><span data-ttu-id="2152f-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="2152f-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-178">11x17</span><span class="sxs-lookup"><span data-stu-id="2152f-178">17</span></span></p></td>
<td><p><span data-ttu-id="2152f-179">說明</span><span class="sxs-lookup"><span data-stu-id="2152f-179">Description</span></span></p></td>
<td><p><span data-ttu-id="2152f-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="2152f-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-181">滿</span><span class="sxs-lookup"><span data-stu-id="2152f-181">18</span></span></p></td>
<td><p><span data-ttu-id="2152f-182">R</span><span class="sxs-lookup"><span data-stu-id="2152f-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="2152f-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="2152f-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-184">合</span><span class="sxs-lookup"><span data-stu-id="2152f-184">19</span></span></p></td>
<td><p><span data-ttu-id="2152f-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="2152f-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="2152f-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="2152f-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-187">20</span><span class="sxs-lookup"><span data-stu-id="2152f-187">20</span></span></p></td>
<td><p><span data-ttu-id="2152f-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="2152f-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="2152f-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="2152f-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-190">99</span><span class="sxs-lookup"><span data-stu-id="2152f-190">99</span></span></p></td>
<td><p><span data-ttu-id="2152f-191">entryID</span><span class="sxs-lookup"><span data-stu-id="2152f-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="2152f-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="2152f-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2152f-193">[**識別碼**] 欄中的數位必須是唯一的，而且絕對不應重複使用。</span><span class="sxs-lookup"><span data-stu-id="2152f-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="2152f-194">此外，在256下保留 ID 值，會節省通訊錄服務器所撰寫的輸出檔案中的空間。</span><span class="sxs-lookup"><span data-stu-id="2152f-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="2152f-195">不過，最大 ID 值是65535。</span><span class="sxs-lookup"><span data-stu-id="2152f-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="2152f-196">[ **Name** ] （名稱）欄對應的是 Active Directory 屬性名稱，而使用者複製器應該放在每個連絡人的 AbUserEntry 表格中。</span><span class="sxs-lookup"><span data-stu-id="2152f-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="2152f-197">[Flags] （**旗**）欄中的值是用來定義屬性類型。</span><span class="sxs-lookup"><span data-stu-id="2152f-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="2152f-198">下列類型的通訊錄服務器屬性可由使用者複製器辨識，並以 [**旗**欄] 中值的低位元組表示。</span><span class="sxs-lookup"><span data-stu-id="2152f-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2152f-199">Attribute</span><span class="sxs-lookup"><span data-stu-id="2152f-199">Attribute</span></span></th>
<th><span data-ttu-id="2152f-200">說明</span><span class="sxs-lookup"><span data-stu-id="2152f-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2152f-201">0x0</span><span class="sxs-lookup"><span data-stu-id="2152f-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="2152f-202">字串屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-202">A string attribute.</span></span> <span data-ttu-id="2152f-203">使用者複製程式將此類型轉換為 UTF-8，然後將它儲存在 AbUserEntry 資料表中。</span><span class="sxs-lookup"><span data-stu-id="2152f-203">User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-204">0x1</span><span class="sxs-lookup"><span data-stu-id="2152f-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="2152f-205">二進位屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-205">A binary attribute.</span></span> <span data-ttu-id="2152f-206">使用者複製程式會將此儲存在 blob 中，而不會轉換。</span><span class="sxs-lookup"><span data-stu-id="2152f-206">User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-207">反</span><span class="sxs-lookup"><span data-stu-id="2152f-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="2152f-208">字串屬性，但只有在屬性值以&quot;電話開頭後才會包含。&quot;</span><span class="sxs-lookup"><span data-stu-id="2152f-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="2152f-209">這主要是針對多值字串屬性，特別是<strong>proxyAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="2152f-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="2152f-210">在此案例中，通訊錄服務器只適用于<strong></strong>以&quot;電話開始的 proxyAddresses 專案：&quot;。</span><span class="sxs-lookup"><span data-stu-id="2152f-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="2152f-211">因此，對於儲存空間的興趣，使用者複製只會儲存以&quot;電話開始的專案：。&quot;</span><span class="sxs-lookup"><span data-stu-id="2152f-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-212">0x3</span><span class="sxs-lookup"><span data-stu-id="2152f-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="2152f-213">布林字串屬性，如果 TRUE，則會導致使用者複製不在 AbUserEntry 資料表中包含此連絡人。</span><span class="sxs-lookup"><span data-stu-id="2152f-213">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table.</span></span> <span data-ttu-id="2152f-214">如果是 FALSE，則會讓使用者複製器在 AbUserEntry 資料表中包含此連絡人的屬性，而不是使用此標誌的特定屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-214">If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag.</span></span> <span data-ttu-id="2152f-215">這是另一個主要的特殊案例類型，主要用於<strong>msExchHideFromAddressLists</strong>屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-215">This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-216">0x4</span><span class="sxs-lookup"><span data-stu-id="2152f-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="2152f-217">字串屬性，但只有在屬性&quot;值以 smtp：&quot;開頭並包含&quot; @ &quot;符號時才包含。</span><span class="sxs-lookup"><span data-stu-id="2152f-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-218">0x5</span><span class="sxs-lookup"><span data-stu-id="2152f-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="2152f-219">字串屬性， &quot;但只有當屬性值以電話：&quot;或&quot;smtp：&quot;開頭，並包含符號時，才會&quot; @ &quot;包含該屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-220">0x100</span><span class="sxs-lookup"><span data-stu-id="2152f-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="2152f-221">如果已設定，這是多重值屬性，每個連絡人可能會出現一次以上的屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-222">0x400</span><span class="sxs-lookup"><span data-stu-id="2152f-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="2152f-223">如果已設定，則會識別連絡人的 [電子郵件使用者帳戶名稱] 屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-223">If set, this identifies the email user account name attribute for a contact.</span></span> <span data-ttu-id="2152f-224">通訊錄服務器使用這個標誌來識別要在電話正常化事件記錄專案中顯示的屬性值。</span><span class="sxs-lookup"><span data-stu-id="2152f-224">Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-225">0x800</span><span class="sxs-lookup"><span data-stu-id="2152f-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="2152f-226">如果已設定，則會識別連絡人的必要屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-226">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="2152f-227">[通訊錄服務器] 只有在 Active Directory 中有這個屬性的值時，才會在 AbUserEntry 表格中包含使用者。</span><span class="sxs-lookup"><span data-stu-id="2152f-227">Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory.</span></span> <span data-ttu-id="2152f-228">如果有一個以上的必要屬性，則只有其中一個屬性需要有一個值，才能在 AbUserEntry 資料表中包含使用者。</span><span class="sxs-lookup"><span data-stu-id="2152f-228">If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="2152f-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="2152f-230">如果已設定，通訊錄服務器會始終正常化這個屬性的值。</span><span class="sxs-lookup"><span data-stu-id="2152f-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="2152f-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="2152f-232">如果已設定，通訊錄服務器會使用<strong>proxyAddresses</strong>中的正常化數位（如果<strong>UseNormalizationRules</strong> CMS 設定為 FALSE）;否則，它的運作方式與旗標位為0x1000 時一樣。</span><span class="sxs-lookup"><span data-stu-id="2152f-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="2152f-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="2152f-234">如果已設定，通訊錄服務器不會將 AbUserEntry 資料表中的物件，包含指定屬性的這個值。</span><span class="sxs-lookup"><span data-stu-id="2152f-234">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute.</span></span> <span data-ttu-id="2152f-235">例如，如果<strong>msRTCSIP-PrimaryUserAddress</strong>屬性有這個標誌位集，則擁有此屬性的連絡人就不會寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="2152f-235">For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="2152f-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="2152f-237">如果已設定，通訊錄服務器不會包含 AbUserEntry 資料表中的物件，對於指定的屬性不會有這個值。</span><span class="sxs-lookup"><span data-stu-id="2152f-237">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute.</span></span> <span data-ttu-id="2152f-238">如果0x4000 和0x8000 標誌位都是在物件上設定，則會優先使用標誌位值設定為0x4000 的屬性，並將該物件排除在 AbUserEntry 資料表中。</span><span class="sxs-lookup"><span data-stu-id="2152f-238">If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="2152f-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="2152f-240">如果已設定，則代表群組物件。</span><span class="sxs-lookup"><span data-stu-id="2152f-240">If set, this represents a group object.</span></span> <span data-ttu-id="2152f-241">使用者複製器使用這個標誌位，將連絡人與<strong>groupType</strong>屬性（例如通訊群組清單或安全性群組）一起包含在其中。</span><span class="sxs-lookup"><span data-stu-id="2152f-241">User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="2152f-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="2152f-243">如果設定，使用者複製器會使用這個標誌位，將此屬性包含在裝置特定的通訊錄服務器檔案（也就是副檔名為 dabs 的檔案）。</span><span class="sxs-lookup"><span data-stu-id="2152f-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2152f-244">在舊版的 Lync Server 中，當您將變更套用至 Active Directory 時，系統會要求系統管理員執行**更新 CSUserDatabase**與**更新– CSAddressBook**的 Windows PowerShell Cmdlet，立即將變更保留在 Lync Server 使用者資料庫和 RTCab 資料庫中。</span><span class="sxs-lookup"><span data-stu-id="2152f-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="2152f-245">在 Lync Server 2013 中，Lync Server 使用者複製程式會從 Active Directory 中挑選變更，並根據設定的間隔更新 Lync Server 使用者資料庫。</span><span class="sxs-lookup"><span data-stu-id="2152f-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="2152f-246">Lync Server 使用者複製程式也會快速傳播 RTCab 資料庫的變更，而不需管理員必須執行更新-CSAddressBook。</span><span class="sxs-lookup"><span data-stu-id="2152f-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="2152f-247">如果已啟用 [通訊錄網頁查詢]，則這些變更將會在搜尋結果中反映 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="2152f-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="2152f-248">如果已啟用通訊錄檔案下載，系統管理員將只需要執行更新 CSAddressBook。</span><span class="sxs-lookup"><span data-stu-id="2152f-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2152f-249">依預設，Lync Server 使用者複製程式每5分鐘自動執行一次。</span><span class="sxs-lookup"><span data-stu-id="2152f-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="2152f-250">您可以使用 CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;來設定此間隔。</span><span class="sxs-lookup"><span data-stu-id="2152f-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="2152f-251">篩選通訊錄</span><span class="sxs-lookup"><span data-stu-id="2152f-251">Filtering the Address Book</span></span>

<span data-ttu-id="2152f-252">在通訊錄服務器檔案中填入的使用者，可以根據 AbAttribute 資料表中所列的特定 Active Directory 網域服務屬性來加以控制。</span><span class="sxs-lookup"><span data-stu-id="2152f-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="2152f-253">其中一個用於篩選的屬性是**msExchangeHideFromAddressBook**屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="2152f-254">這是 Exchange 架構新增的使用者屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="2152f-255">如果此屬性的值為 TRUE，Exchange Server 會使用此屬性來從 Outlook 全域通訊清單（GAL）中隱藏連絡人。</span><span class="sxs-lookup"><span data-stu-id="2152f-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="2152f-256">同樣地，如果此屬性的值為 TRUE，則使用者複製程式不會將該使用者包含在 AbUserEntry 資料表中，而且此使用者將不會在通訊錄服務器檔案中。</span><span class="sxs-lookup"><span data-stu-id="2152f-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="2152f-257">您可以使用一些標誌位來定義要在通訊錄服務器屬性上使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="2152f-257">You can use some flag bits to define a filter to use on Address Book Server attributes.</span></span> <span data-ttu-id="2152f-258">例如，某些旗標位的存在可以將屬性識別為 include 屬性或 exclude 屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-258">For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute.</span></span> <span data-ttu-id="2152f-259">使用者複製程式會篩選出包含 exclude 屬性的連絡人，而篩選掉包含的內容不包含 include 屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-259">User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2152f-260">如需篩選通訊錄的詳細資訊，請參閱<A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Lync server 2013 中的通訊錄服務器 Cmdlet</A>，以及<A href="http://go.microsoft.com/fwlink/?linkid=330430">篩選 lync 2013 通訊錄</A></span><span class="sxs-lookup"><span data-stu-id="2152f-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="2152f-261">目前有三種不同的篩選。</span><span class="sxs-lookup"><span data-stu-id="2152f-261">Currently, there are three different filters.</span></span> <span data-ttu-id="2152f-262">下表列出這些篩選。</span><span class="sxs-lookup"><span data-stu-id="2152f-262">The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2152f-263">Attribute</span><span class="sxs-lookup"><span data-stu-id="2152f-263">Attribute</span></span></th>
<th><span data-ttu-id="2152f-264">說明</span><span class="sxs-lookup"><span data-stu-id="2152f-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2152f-265">0x800</span><span class="sxs-lookup"><span data-stu-id="2152f-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="2152f-266">如果已設定，則會識別連絡人的必要屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-266">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="2152f-267">使用者複製程式使用這個標誌位來篩選不含至少一個必要屬性的連絡人。</span><span class="sxs-lookup"><span data-stu-id="2152f-267">User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute.</span></span> <span data-ttu-id="2152f-268">OuPathId 是必要的屬性，它會永遠設定。</span><span class="sxs-lookup"><span data-stu-id="2152f-268">The OuPathId is a required attribute, which is always set.</span></span> <span data-ttu-id="2152f-269">因此，必須設定至少一個必要的屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-269">So at least one of other required attributes should be set.</span></span> <span data-ttu-id="2152f-270">否則，contact （也就是 [必要屬性 OuPathId] 的值）仍不會寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="2152f-270">Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database.</span></span> <span data-ttu-id="2152f-271">例如，如果<strong>telephonenumber 相同</strong>和<strong>homePhone</strong>是定義為必要的屬性，則只有至少有其中一個屬性的連絡人會寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="2152f-271">For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2152f-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="2152f-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="2152f-273">如果設定，就會識別 [排除] 屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-273">If set, this identifies an exclude attribute.</span></span> <span data-ttu-id="2152f-274">使用者複製程式使用這個標誌位來篩選出包含這個屬性的連絡人。</span><span class="sxs-lookup"><span data-stu-id="2152f-274">User Replicator uses this flag bit to filter out contacts that contain this attribute.</span></span> <span data-ttu-id="2152f-275">例如，如果<strong>msRTCSIP-PrimaryUserAddress</strong>定義為 exclude 屬性，則擁有此屬性的連絡人就不會寫入資料庫中。</span><span class="sxs-lookup"><span data-stu-id="2152f-275">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2152f-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="2152f-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="2152f-277">如果設定，就會識別包含屬性。</span><span class="sxs-lookup"><span data-stu-id="2152f-277">If set, this identifies an include attribute.</span></span> <span data-ttu-id="2152f-278">使用者複製程式使用這個標誌位來篩選不含此屬性的連絡人。</span><span class="sxs-lookup"><span data-stu-id="2152f-278">User Replicator uses this flag bit to filter out contacts that do not contain this attribute.</span></span> <span data-ttu-id="2152f-279">例如，如果<strong>msRTCSIP-PrimaryUserAddress</strong>定義為 include 屬性，則只有擁有此屬性的連絡人會寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="2152f-279">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2152f-280">如果0x4000 （exclude 屬性）和0x8000 （include 屬性）標誌位都已設定，則0x4000 位會覆寫0x8000 位，且會排除該連絡人。</span><span class="sxs-lookup"><span data-stu-id="2152f-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="2152f-281">雖然您可以將通訊錄篩選為僅包含特定使用者，但限制專案不會限制其他使用者與篩選的使用者聯繫，或查看其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="2152f-281">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status.</span></span> <span data-ttu-id="2152f-282">使用者可以在通訊錄中輸入使用者完整的登入名稱，隨時能找到、手動傳送立即訊息，或手動啟動呼叫給不在通訊錄中的使用者。</span><span class="sxs-lookup"><span data-stu-id="2152f-282">Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name.</span></span> <span data-ttu-id="2152f-283">此外，也可以在 Outlook 中找到使用者的連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="2152f-283">Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="2152f-284">在通訊錄檔案中有完整的連絡人記錄，讓您可以使用 Lync Server 來啟動電子郵件、電話或企業語音通話（也就是在伺服器上啟用企業語音通話），而使用者並未針對會話初始化進行設定通訊協定（SIP），某些組織想要在通訊錄服務器專案中只包含啟用 SIP 的使用者。</span><span class="sxs-lookup"><span data-stu-id="2152f-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="2152f-285">您可以透過清除下列必要屬性的**Flags**欄中的0x800 位來篩選通訊錄，只包含啟用 SIP 的使用者： **mailNickname**、 **telephonenumber 相同**、 **homePhone**和**mobile**。</span><span class="sxs-lookup"><span data-stu-id="2152f-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="2152f-286">您也可以透過在**msRTCSIP-PrimaryUserAddress**屬性的 [**旗標**] 欄中設定0x8000 （包含屬性），來篩選通訊錄，以便只包含啟用 SIP 的使用者。</span><span class="sxs-lookup"><span data-stu-id="2152f-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="2152f-287">這也有助於將服務帳戶從通訊錄檔案中排除。</span><span class="sxs-lookup"><span data-stu-id="2152f-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="2152f-288">修改 AbAttribute 資料表之後，您可以執行 Cmdlet**更新-CsUserDatabase**命令，以重新整理 AbUserEntry 資料表中的資料。</span><span class="sxs-lookup"><span data-stu-id="2152f-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="2152f-289">在 UR 複製完成後，您可以透過手動執行 Cmdlet **UpdateCsAddressBook**命令，在通訊錄服務器檔儲存區中更新檔案。</span><span class="sxs-lookup"><span data-stu-id="2152f-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2152f-290">[通訊錄服務器] 所在的前端伺服器不是由管理的方式設定。</span><span class="sxs-lookup"><span data-stu-id="2152f-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="2152f-291">在部署期間選擇一個，通常是部署的第一台前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="2152f-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="2152f-292">在發生失敗時，通訊錄服務將會移至另一個前端伺服器，且不需要系統管理方面的注意。</span><span class="sxs-lookup"><span data-stu-id="2152f-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2152f-293">如果您已從多目錄林部署或父/子部署（例如先整合您的基礎結構，然後再移至 Lync Server）進行合併或修改，您可能會發現通訊錄服務下載，且通訊錄網頁查詢無法供某些使用者使用。</span><span class="sxs-lookup"><span data-stu-id="2152f-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="2152f-294">當您在具有多個網域或樹林的部署中時，會在出現問題的使用者物件上填入屬性<STRONG>MsRTCSIP-OriginatorSid</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="2152f-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="2152f-295">在這些物件上， <STRONG>MsRTCSIP-OriginatorSid</STRONG>屬性必須設定為 Null，才能解決問題。</span><span class="sxs-lookup"><span data-stu-id="2152f-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

