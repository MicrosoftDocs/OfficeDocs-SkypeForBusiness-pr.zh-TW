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
ms.openlocfilehash: 45dbc2c71cf34515f8f6176e4f579e6683ad319e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>管理 Lync Server 2013 中的通訊錄服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-05_

部署 Lync Server，Enterprise Edition 或 Standard Edition server 的一部分，預設會安裝通訊錄服務。 通訊錄服務 – RTCab – 所使用的資料庫建立 SQL Server 上 (這是後端 SQL Server Enterprise Edition，; Standard Edition server，組合的 SQL 伺服器)。

<div>


> [!NOTE]  
> 如需使用<STRONG>Adsi</STRONG>編輯 Active Directory 網域服務物件的屬性的詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/?linkid=330427">Adsi 編輯器]</A>。 特別針對通訊錄服務 Resource kit 工具的詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit 工具</A>。



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>Address Book Server 電話號碼正規化

Lync Server 需要標準化的 RFC 3966/E.164 電話號碼。 若要使用非結構化或不一致的格式化的電話號碼，Lync Server 依賴 Address Book Server 之前他們所要的正規化規則交給預先處理的電話號碼。 當通訊錄中使用的電話號碼正規化規則會套用，例如 Lync Phone Edition 和 Lync 行動用戶端可以使用這些正規化的號碼。

舊版中使用的正規化規則可能需要經過一些調整才能正常使用。因為在交給正規化規則之前會先移除空格和非強制字元，所以如果 regex 運算式明確尋找虛線或其他已移除的字元，正規化規則可能會失敗。您應該檢閱正規化規則，確保它們不會尋找這類非強制字元，否則，如果規則預期字元存在而字元不存在，規則就會先按正常程序失敗再繼續運作。

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>使用者複寫器和 Address Book Server

Address Book Server 會使用 [使用者複寫器] 提供的資料，來更新其最初從全域通訊清單 (GAL) 取得的資訊。 使用者複寫器寫入每個使用者、 連絡人及群組到 AbUserEntry 資料庫資料表中的 Active Directory 網域服務屬性和 Address Book Server 會同步到檔案中的 Address Book Server 檔案存放區資料庫中的使用者資料和通訊錄中輸入資料庫 RTCab。 AbUserEntry 資料表的架構使用兩個資料行 **UserGuid** 和 **UserData**。 **UserGuid**是在索引資料欄，並包含 Active Directory 物件的 16 位元組 GUID。 **UserData**為影像資料行包含的所有連絡人的先前所述的 Active Directory 網域服務屬性。

使用者複寫器會決定藉由讀取組態資料表位於相同的 SQL server 執行個體作為 AbUserEntry 表格來撰寫哪些 Active Directory 屬性。 AbAttribute 資料表包含三個資料行 **ID**、**Name**、**Flags** 和 **Enable**。 此資料表是在資料庫設定期間建立。 如果 AbAttribute 資料表是空的，[使用者複寫器] 會略過其 AbUserEntry 資料表處理邏輯。 Address Book Server 屬性是從 AbAttribute 資料表擷取的動態屬性，該資料表最初是在 Address Book Server 啟動時由 Address Book Server 寫入。

Address Book Server 啟用填入 AbAttribute 表格，如下表所示的值。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>識別碼</th>
<th>名稱</th>
<th>Flags</th>
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
<td><p>Sn</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>標題</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>Company</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>包含 PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>住家電話</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11 </p></td>
<td><p>行動裝置</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13 </p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14 </p></td>
<td><p>郵件</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15 </p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16 </p></td>
<td><p>部門</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17 </p></td>
<td><p>描述</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18 </p></td>
<td><p>管理員</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>19</p></td>
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


**ID** 資料行中的數字必須是唯一的，且絕不可重複使用。 另外，保持 ID 值小於 256 可在 Address Book Server 寫入的輸出檔中節省空間。 不過，ID 最大值是 65535。 [**名稱**] 欄會對應至使用者複寫器應該放 AbUserEntry 資料表中的每個連絡人的 Active Directory 屬性名稱。 **Flags** 資料行中的值用來定義屬性的類型。 [使用者複寫器] 認得下列類型的 Address Book Server 屬性 (以 **Flags** 資料行中的值的低位元組表示)。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>屬性</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>字串屬性。[使用者複寫器] 會先將此類型轉換為 UTF-8，再將之儲存於 AbUserEntry 資料表。</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>二進位屬性。[使用者複寫器] 會以二進位大型物件儲存此屬性而不做任何轉換。</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>字串屬性，但時才包含屬性值開頭&quot;tel:&quot;。 這主要用於多重值字串屬性，特別是 <strong>proxyAddresses</strong>。 在此情況下，Address Book Server 會有興趣僅開頭的<strong>proxyAddresses</strong>項目&quot;tel:&quot;。 因此，以儲存空間，使用者複寫器會儲存開頭的項目&quot;tel:&quot;。</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>布林字串屬性，TRUE 會使 [使用者複寫器] 不將此連絡人放入 AbUserEntry 資料表中。如果是 FALSE，則會使 [使用者複寫器] 將此連絡人的屬性放入 AbUserEntry 資料表中，但不包括具有此旗標的特定屬性。這是另一個主要用於 <strong>msExchHideFromAddressLists</strong> 屬性的特殊案例類型。</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>字串屬性，但時才包含屬性值開頭&quot;smtp:&quot; ，並包含&quot; @ &quot;符號。</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>字串屬性，但時才包含屬性值開頭為&quot;tel:&quot;或&quot;smtp:&quot; ，並包含&quot; @ &quot;符號。</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>如果設定，則這是可針對每個連絡人出現一次以上的多重值屬性。</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>如果設定，則這將識別連絡人的電子郵件使用者帳戶名稱屬性。Address Book Server 會使用此旗標來識別要在電話正規化事件記錄項目中顯示的屬性值。</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>如果設定，則這將識別連絡人的必要屬性。只有當此屬性在 Active Directory 中有值時，Address Book Server 才會在 AbUserEntry 資料表中加入使用者。如果有一個以上的必要屬性，則只要其中一個有值，就會在 AbUserEntry 資料表中加入使用者。</p></td>
</tr>
<tr class="even">
<td><p>0x1000 時相同</p></td>
<td><p>如果設定，則 Address Book Server 一律會正規化此屬性的值。</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>如果設定，則當 <strong>UseNormalizationRules</strong> CMS 設定為 FALSE 時，Address Book Server 會使用 <strong>proxyAddresses</strong> 中的正規化數字，否則其行為與旗標位元為 0x1000 時相同。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>如果設定，則 Address Book Server 不會在 AbUserEntry 資料表中加入所指定的屬性為此值的物件。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 屬性已設定此旗標位元，則不會將具有此屬性的連絡人寫入資料庫。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>如果設定，則 Address Book Server 不會將所指定的屬性不是此值的物件加入 AbUserEntry 資料表。如果物件上同時設定 0x4000 和 0x8000 旗標位元，則以旗標位元值設為 0x4000 的屬性為優先，且會從 AbUserEntry 資料表中排除物件。</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>如果設定，則這代表群組物件。[使用者複寫器] 會使用此旗標位元來加入具有 <strong>groupType</strong> 屬性 (表示這是群組) 的連絡人，例如，通訊群組清單或安全性群組。</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>如果設定，則 [使用者複寫器] 會使用此旗標位元將此屬性加入裝置特定 Address Book Server 檔案 (副檔名為 .dabs 的檔案)。</p></td>
</tr>
</tbody>
</table>


在舊版的 Lync Server，將變更套用至 Active Directory 時，系統管理員就必須執行**更新-CSUserDatabase**與**更新 – CSAddressBook** Windows PowerShell cmdlet 可立即保存 RTCab 資料庫與 Lync Server 使用者資料庫的變更。 在 Lync Server 2013 中，Lync Server 使用者複寫器會挑選來自 Active Directory 所做的變更，並更新 Lync Server 使用者資料庫，根據設定的間隔。 Lync Server 使用者複寫器會也將變更傳播到 RTCab 資料庫快速而不必執行 Update-csaddressbook 系統管理員。 如果已啟用地址通訊錄 Web 查詢，然後所做的變更會反映在搜尋結果中 Lync 用戶端。 系統管理員只將必須重新執行 Update-csaddressbook，如果已啟用 Address Book 檔案下載。

<div>


> [!NOTE]  
> 根據預設 Lync Server 使用者複寫器會自動執行每隔 5 分鐘。 您可以使用 Set CSUserReplicatorConfiguration 來設定此間隔-ReplicationCycleInterval &lt; &gt;。



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>篩選通訊錄

您可以根據 AbAttribute 表所列的特定 Active Directory 網域服務屬性控制填入 Address Book Server 檔案中的使用者。 其中一個這類可用於篩選的屬性就是 **msExchangeHideFromAddressBook** 屬性。 這是由 Exchange 架構所新增的使用者屬性。 如果此屬性的值是 TRUE，Exchange Server 會使用此屬性在 Outlook 全域通訊清單 (GAL) 隱藏該連絡人。 同樣地，如果此屬性的值是 TRUE，[使用者複寫器] 不會在 AbUserEntry 資料表中加入該使用者，而此使用者不會出現在 Address Book Server 檔案中。

您可以使用一些旗標位元來定義要在 Address Book Server 屬性上使用的篩選器。例如，某些旗標位元的存在可將屬性識別為包含屬性或排除屬性。[使用者複寫器] 會濾除含有排除屬性的連絡人，並濾除不含包含屬性的連絡人。

<div>


> [!WARNING]  
> 如需篩選通訊錄的詳細資訊，請參閱<A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Lync Server 2013 中的 Address Book Server cmdlet</A>，並<A href="https://go.microsoft.com/fwlink/?linkid=330430">篩選 Lync 2013 通訊錄</A>



</div>

目前，有三種不同的篩選器。下表列出這些篩選器。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>屬性</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>如果設定，則這將識別連絡人的必要屬性。[使用者複寫器] 會使用此旗標位元來濾除不含至少一個必要屬性的連絡人。OuPathId 是一律會設定的必要屬性。因此，至少應該再設定另一個必要屬性。否則，仍然不會將連絡人 (具有必要屬性 OuPathId 的值) 寫入資料庫。例如，如果 <strong>telephoneNumber</strong> 和 <strong>homePhone</strong> 是定義為必要屬性，則只會將具有至少其中一個屬性的連絡人寫入資料庫。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>如果設定，則這將識別排除屬性。[使用者複寫器] 會使用此旗標位元來濾除包含此屬性的連絡人。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 是定義為排除屬性，則不會將具有此屬性的連絡人寫入資料庫。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>如果設定，則這將識別包含屬性。[使用者複寫器] 會使用此旗標位元來濾除不含此屬性的連絡人。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 是定義為包含屬性，則只會將具有此屬性的連絡人寫入資料庫。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 如果同時設定 0x4000 (排除屬性) 和 0x8000 (包含屬性) 旗標位元，則 0x4000 位元會覆寫 0x8000 位元，並排除該連絡人。



</div>

雖然您可以篩選通訊錄來僅包含某些使用者，但限制項目並不會限制其他使用者連絡被濾除的使用者，或查看其顯示狀態的能力。使用者一律可以輸入使用者的完整登入名稱，以尋找不在通訊錄中的使用者，或是對其手動傳送即時訊息或手動進行呼叫。另外，在 Outlook 中也可以找到使用者的連絡資訊。

Address Book 檔案中具有完整連絡人記錄可讓您使用 Lync Server，啟動電子郵件，而電話或 Enterprise Voice 通話 （亦即，如果在伺服器上啟用 Enterprise Voice） 與未設定的工作階段初始的使用者通訊協定 (SIP)，有些組織想要在其 Address Book Server 項目中包含只有已啟用 SIP 的使用者。 您可以篩選通訊錄若要清除 0x800 位元**旗標**] 欄中的下列必要的屬性包含只有已啟用 SIP 的使用者： **mailNickname**、 **telephoneNumber**、**住家電話**，以及**行動裝置**。 您也可以篩選通訊錄加入只有已啟用 SIP 的使用者藉由設定 0x8000 （包含屬性） 的**Msrtcsip-primaryuseraddress**屬性的**旗標**] 欄中。 這也有助於排除通訊錄檔案的服務帳戶。

修改 AbAttribute 資料表之後，您可以執行 Cmdlet **Update-CsUserDatabase** 命令，以重新整理 AbUserEntry 資料表中的資料。 在 UR 複寫完成之後，您可以手動執行 Cmdlet **UpdateCsAddressBook** 命令，以更新 Address Book Server 檔案存放區中的檔案。

<div>


> [!NOTE]  
> 前端伺服器所在 Address Book Server 不行政規定必須加以設定。 其中一個會選擇在部署期間，通常是第一個前端伺服器部署。 發生失敗，通訊錄服務將會移到另一個前端伺服器，並請注意您沒有系統管理。



</div>

<div>


> [!IMPORTANT]  
> 如果您有合併或修改您從多重樹系部署或 （例如移至 Lync Server 之前合併您的基礎結構） 的父系/子系部署的基礎結構，您可能會發現部分使用者下載通訊錄服務和通訊錄 Web 查詢失敗。 在具有多個網域或樹系的部署中，出現此問題的使用者物件上已填入屬性 <STRONG>MsRTCSIP-OriginatorSid</STRONG>。 您必須將這些物件的 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 屬性設為 NULL，才能解決此問題。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

