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

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>在 Lync Server 2013 中管理通訊錄服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

在 Lync Server、Enterprise Edition 或 Standard Edition Server 的部署中，預設會安裝通訊錄服務。 通訊錄服務所使用的資料庫– RTCab –是在 SQL Server 上建立（適用于企業版），這是後端 SQL Server; 針對標準版伺服器，則是 collocated SQL Server）。

<div>


> [!NOTE]  
> 如需使用<STRONG>Adsi 編輯</STRONG>來編輯 Active Directory 網域服務物件屬性的詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI 編輯</A>。 如需有關專門用於通訊錄服務之資源套件中之工具的詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 資源套件工具</A>。



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>通訊錄服務器電話號碼正規化

Lync Server 需要標準化的 RFC 3966/E. 164 個電話號碼。 若要使用非結構化或格式不一致的電話號碼，Lync Server 依賴通訊錄服務器來預處理電話號碼，然後再將其移交給正常化規則。 在通訊錄中使用電話號碼並套用正常化規則時，用戶端（例如 Lync 手機版和 Lync Mobile）都可以使用這些標準化的數位。

在舊版中使用的正常化規則可能無法正常運作，無需進行一些調整。 因為將在正常化規則之前移除空白和非強制字元，所以如果您的 RegEx 運算式特別尋找的是虛線或其他已移除的字元，您的正常化規則可能會失敗。 您應該檢查您的正常化規則，以確保它們無法尋找這些非強制字元，或規則可能會順利失敗，並在規則預期會出現時，繼續執行該字元。

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>使用者複製程式和通訊錄服務器

通訊錄服務器會使用使用者複製器提供的資料，來更新它最初從全域通訊清單（GAL）中獲得的資訊。 使用者複製程式會將每個使用者、連絡人和群組的 Active Directory 網域服務屬性寫入資料庫中的 AbUserEntry 資料表，而通訊錄服務器會將資料庫中的使用者資料同步處理到通訊錄服務器檔存放區中的檔案，並到通訊錄資料庫 RTCab。 AbUserEntry 資料表的架構使用兩個數據行， **UserGuid**與**UserData**。 **UserGuid**是 [索引] 資料行，包含 Active Directory 物件的16個位元組 GUID。 **UserData**是一個 image 欄，其中包含該連絡人所有先前提及的 Active Directory 網域服務屬性。

使用者複製程式會透過讀取位於同一 SQL Server 型實例中的設定資料表，以 AbUserEntry 資料表來決定要寫入哪些 Active Directory 屬性。 AbAttribute 資料表包含三個數據行、**識別碼**、**名稱**、**標記**，以及**Enable**。 資料表是在建立資料庫期間建立的。 如果 AbAttribute 資料表是空的，使用者複製程式會跳過其 AbUserEntry table 處理邏輯。 [通訊錄服務器] 屬性是動態的，而且是從 AbAttribute 資料表中檢索，在通訊錄服務器啟動時，由通訊錄服務器最初撰寫。

通訊錄服務器啟用會以下表中顯示的值來填入 AbAttribute 資料表。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>標識號</th>
<th>名稱</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>Sn.exe</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>職稱</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>500</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>家</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>utf-7</p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>型</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>Telephonenumber 相同</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>第</p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11</p></td>
<td><p>行動裝置</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>之間</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>合</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>郵遞</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>工資</p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>位</p></td>
<td><p>部門</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>11x17</p></td>
<td><p>說明</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>滿</p></td>
<td><p>R</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>合</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>20</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>entryID</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


[**識別碼**] 欄中的數位必須是唯一的，而且絕對不應重複使用。 此外，在256下保留 ID 值，會節省通訊錄服務器所撰寫的輸出檔案中的空間。 不過，最大 ID 值是65535。 [ **Name** ] （名稱）欄對應的是 Active Directory 屬性名稱，而使用者複製器應該放在每個連絡人的 AbUserEntry 表格中。 [Flags] （**旗**）欄中的值是用來定義屬性類型。 下列類型的通訊錄服務器屬性可由使用者複製器辨識，並以 [**旗**欄] 中值的低位元組表示。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribute</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>字串屬性。 使用者複製程式將此類型轉換為 UTF-8，然後將它儲存在 AbUserEntry 資料表中。</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>二進位屬性。 使用者複製程式會將此儲存在 blob 中，而不會轉換。</p></td>
</tr>
<tr class="odd">
<td><p>反</p></td>
<td><p>字串屬性，但只有在屬性值以&quot;電話開頭後才會包含。&quot; 這主要是針對多值字串屬性，特別是<strong>proxyAddresses</strong>。 在此案例中，通訊錄服務器只適用于<strong></strong>以&quot;電話開始的 proxyAddresses 專案：&quot;。 因此，對於儲存空間的興趣，使用者複製只會儲存以&quot;電話開始的專案：。&quot;</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>布林字串屬性，如果 TRUE，則會導致使用者複製不在 AbUserEntry 資料表中包含此連絡人。 如果是 FALSE，則會讓使用者複製器在 AbUserEntry 資料表中包含此連絡人的屬性，而不是使用此標誌的特定屬性。 這是另一個主要的特殊案例類型，主要用於<strong>msExchHideFromAddressLists</strong>屬性。</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>字串屬性，但只有在屬性&quot;值以 smtp：&quot;開頭並包含&quot; @ &quot;符號時才包含。</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>字串屬性， &quot;但只有當屬性值以電話：&quot;或&quot;smtp：&quot;開頭，並包含符號時，才會&quot; @ &quot;包含該屬性。</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>如果已設定，這是多重值屬性，每個連絡人可能會出現一次以上的屬性。</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>如果已設定，則會識別連絡人的 [電子郵件使用者帳戶名稱] 屬性。 通訊錄服務器使用這個標誌來識別要在電話正常化事件記錄專案中顯示的屬性值。</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>如果已設定，則會識別連絡人的必要屬性。 [通訊錄服務器] 只有在 Active Directory 中有這個屬性的值時，才會在 AbUserEntry 表格中包含使用者。 如果有一個以上的必要屬性，則只有其中一個屬性需要有一個值，才能在 AbUserEntry 資料表中包含使用者。</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>如果已設定，通訊錄服務器會始終正常化這個屬性的值。</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>如果已設定，通訊錄服務器會使用<strong>proxyAddresses</strong>中的正常化數位（如果<strong>UseNormalizationRules</strong> CMS 設定為 FALSE）;否則，它的運作方式與旗標位為0x1000 時一樣。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>如果已設定，通訊錄服務器不會將 AbUserEntry 資料表中的物件，包含指定屬性的這個值。 例如，如果<strong>msRTCSIP-PrimaryUserAddress</strong>屬性有這個標誌位集，則擁有此屬性的連絡人就不會寫入資料庫。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>如果已設定，通訊錄服務器不會包含 AbUserEntry 資料表中的物件，對於指定的屬性不會有這個值。 如果0x4000 和0x8000 標誌位都是在物件上設定，則會優先使用標誌位值設定為0x4000 的屬性，並將該物件排除在 AbUserEntry 資料表中。</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>如果已設定，則代表群組物件。 使用者複製器使用這個標誌位，將連絡人與<strong>groupType</strong>屬性（例如通訊群組清單或安全性群組）一起包含在其中。</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>如果設定，使用者複製器會使用這個標誌位，將此屬性包含在裝置特定的通訊錄服務器檔案（也就是副檔名為 dabs 的檔案）。</p></td>
</tr>
</tbody>
</table>


在舊版的 Lync Server 中，當您將變更套用至 Active Directory 時，系統會要求系統管理員執行**更新 CSUserDatabase**與**更新– CSAddressBook**的 Windows PowerShell Cmdlet，立即將變更保留在 Lync Server 使用者資料庫和 RTCab 資料庫中。 在 Lync Server 2013 中，Lync Server 使用者複製程式會從 Active Directory 中挑選變更，並根據設定的間隔更新 Lync Server 使用者資料庫。 Lync Server 使用者複製程式也會快速傳播 RTCab 資料庫的變更，而不需管理員必須執行更新-CSAddressBook。 如果已啟用 [通訊錄網頁查詢]，則這些變更將會在搜尋結果中反映 Lync 用戶端。 如果已啟用通訊錄檔案下載，系統管理員將只需要執行更新 CSAddressBook。

<div>


> [!NOTE]  
> 依預設，Lync Server 使用者複製程式每5分鐘自動執行一次。 您可以使用 CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;來設定此間隔。



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>篩選通訊錄

在通訊錄服務器檔案中填入的使用者，可以根據 AbAttribute 資料表中所列的特定 Active Directory 網域服務屬性來加以控制。 其中一個用於篩選的屬性是**msExchangeHideFromAddressBook**屬性。 這是 Exchange 架構新增的使用者屬性。 如果此屬性的值為 TRUE，Exchange Server 會使用此屬性來從 Outlook 全域通訊清單（GAL）中隱藏連絡人。 同樣地，如果此屬性的值為 TRUE，則使用者複製程式不會將該使用者包含在 AbUserEntry 資料表中，而且此使用者將不會在通訊錄服務器檔案中。

您可以使用一些標誌位來定義要在通訊錄服務器屬性上使用的篩選。 例如，某些旗標位的存在可以將屬性識別為 include 屬性或 exclude 屬性。 使用者複製程式會篩選出包含 exclude 屬性的連絡人，而篩選掉包含的內容不包含 include 屬性。

<div>


> [!WARNING]  
> 如需篩選通訊錄的詳細資訊，請參閱<A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Lync server 2013 中的通訊錄服務器 Cmdlet</A>，以及<A href="http://go.microsoft.com/fwlink/?linkid=330430">篩選 lync 2013 通訊錄</A>



</div>

目前有三種不同的篩選。 下表列出這些篩選。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribute</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>如果已設定，則會識別連絡人的必要屬性。 使用者複製程式使用這個標誌位來篩選不含至少一個必要屬性的連絡人。 OuPathId 是必要的屬性，它會永遠設定。 因此，必須設定至少一個必要的屬性。 否則，contact （也就是 [必要屬性 OuPathId] 的值）仍不會寫入資料庫。 例如，如果<strong>telephonenumber 相同</strong>和<strong>homePhone</strong>是定義為必要的屬性，則只有至少有其中一個屬性的連絡人會寫入資料庫。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>如果設定，就會識別 [排除] 屬性。 使用者複製程式使用這個標誌位來篩選出包含這個屬性的連絡人。 例如，如果<strong>msRTCSIP-PrimaryUserAddress</strong>定義為 exclude 屬性，則擁有此屬性的連絡人就不會寫入資料庫中。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>如果設定，就會識別包含屬性。 使用者複製程式使用這個標誌位來篩選不含此屬性的連絡人。 例如，如果<strong>msRTCSIP-PrimaryUserAddress</strong>定義為 include 屬性，則只有擁有此屬性的連絡人會寫入資料庫。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 如果0x4000 （exclude 屬性）和0x8000 （include 屬性）標誌位都已設定，則0x4000 位會覆寫0x8000 位，且會排除該連絡人。



</div>

雖然您可以將通訊錄篩選為僅包含特定使用者，但限制專案不會限制其他使用者與篩選的使用者聯繫，或查看其目前狀態。 使用者可以在通訊錄中輸入使用者完整的登入名稱，隨時能找到、手動傳送立即訊息，或手動啟動呼叫給不在通訊錄中的使用者。 此外，也可以在 Outlook 中找到使用者的連絡人資訊。

在通訊錄檔案中有完整的連絡人記錄，讓您可以使用 Lync Server 來啟動電子郵件、電話或企業語音通話（也就是在伺服器上啟用企業語音通話），而使用者並未針對會話初始化進行設定通訊協定（SIP），某些組織想要在通訊錄服務器專案中只包含啟用 SIP 的使用者。 您可以透過清除下列必要屬性的**Flags**欄中的0x800 位來篩選通訊錄，只包含啟用 SIP 的使用者： **mailNickname**、 **telephonenumber 相同**、 **homePhone**和**mobile**。 您也可以透過在**msRTCSIP-PrimaryUserAddress**屬性的 [**旗標**] 欄中設定0x8000 （包含屬性），來篩選通訊錄，以便只包含啟用 SIP 的使用者。 這也有助於將服務帳戶從通訊錄檔案中排除。

修改 AbAttribute 資料表之後，您可以執行 Cmdlet**更新-CsUserDatabase**命令，以重新整理 AbUserEntry 資料表中的資料。 在 UR 複製完成後，您可以透過手動執行 Cmdlet **UpdateCsAddressBook**命令，在通訊錄服務器檔儲存區中更新檔案。

<div>


> [!NOTE]  
> [通訊錄服務器] 所在的前端伺服器不是由管理的方式設定。 在部署期間選擇一個，通常是部署的第一台前端伺服器。 在發生失敗時，通訊錄服務將會移至另一個前端伺服器，且不需要系統管理方面的注意。



</div>

<div>


> [!IMPORTANT]  
> 如果您已從多目錄林部署或父/子部署（例如先整合您的基礎結構，然後再移至 Lync Server）進行合併或修改，您可能會發現通訊錄服務下載，且通訊錄網頁查詢無法供某些使用者使用。 當您在具有多個網域或樹林的部署中時，會在出現問題的使用者物件上填入屬性<STRONG>MsRTCSIP-OriginatorSid</STRONG> 。 在這些物件上， <STRONG>MsRTCSIP-OriginatorSid</STRONG>屬性必須設定為 Null，才能解決問題。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

