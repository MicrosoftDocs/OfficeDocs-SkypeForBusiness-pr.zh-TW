---
title: Lync 中使用者相片的顯示方式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd3214c3ada87db6f44f6b99373346d4f0a27d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Lync 中使用者相片的顯示方式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-25_

**摘要：** 根據您所使用的 Lync 功能（例如在會議或 IM 聊天中時），在 Lync 用戶端上顯示的使用者相片可能會有所不同。

Lync 2010 引進了將相片與您的 Lync 設定檔一起提供給其他 Lync 使用者的功能。 您也可以選擇是否要在 Lync 用戶端中顯示連絡人的相片。 在 Lync 2013 中，為使用者提供高解析度相片的支援。 本主題說明 Lync 用戶端如何取得及顯示使用者相片、儲存影像的位置、每個影像來源的限制，以及使用者相片如何由不同的 Lync 服務使用。

<div>

## <a name="planning-considerations"></a>規劃考慮

規劃執行使用者相片支援時，請考慮下列事項。

  - 高定義使用者相片支援要求使用者的信箱位於 Exchange 2013，而 Lync 使用者帳戶位於 Lync 2013 池中。

  - 只有在使用 Lync Server 2013 與 Exchange 2013 的環境中，才能支援高定義使用者相片。

  - 在 Exchange 2010 上擁有信箱的使用者，將永遠會使用**thumbnailPhoto**屬性（從 AD DS 做為其使用者相片的來源）。

  - 從 AD DS 儲存為**thumbnailPhoto**屬性的使用者相片，不會顯示在外部/同盟連絡人。

  - 如果使用者連絡人的相片儲存在 AD DS 中，則所使用的圖像檔案將限制為96×96圖元且不超過 100 KB 的檔案大小。

  - 如果 Lync Server 與 Exchange Server 之間的連線能力遺失，就會顯示使用者的來自 AD DS 的低解析度**thumbnailPhoto** ，且僅供內部使用者使用。

  - 當使用中的喇叭沒有啟用影片時，會在 Lync 2013 會議中顯示高解析度的使用者相片。 此外，將滑鼠移到圖庫中的縮圖相片上方，就會顯示高解析度相片。

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Lync 2010 中的使用者相片

在 Lync 2010 用戶端中，您可以選擇兩種選項來顯示設定檔的相片、**預設的 [公司圖片**]，以及 [**從網址顯示圖片**]。

<div>

## <a name="default-corporate-picture"></a>預設的公司圖片

當您選擇 [**預設的公司圖片**] 選項時，Lync 會從 Active Directory 網域服務取得為您顯示的相片。 所使用的影像是在 Active Directory 網域服務中定義為**thumbnailPhoto**屬性值的影像。 這是 Exchange 在 Outlook 中顯示影像時所使用的相同檔案。

使用 Active Directory 網域服務中的影像時的考慮事項如下：

  - 僅支援最大為96圖元乘96圖元的影像。 影像的檔案大小限制為 100 KB。

  - 根據預設，使用者可以變更**thumbnailPhoto**屬性所使用的影像，但不直接透過 Lync 用戶端進行。 您可以透過 Active Directory 網域服務停用此狀態。

  - 儲存在 Active Directory 網域服務中的圖像，不會顯示給您組織外部的連絡人，即使他們是同盟連絡人也一樣。

  - 在大型組織中，針對大量使用者儲存及檢索影像，可能會影響 Active Directory 網域服務資料庫的大小和效能。

  - 受限制的圖像尺寸與檔案大小代表只有低解析度影像可供使用。

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>使用者如何在 Active Directory 網域服務中管理使用者的相片

使用者無法透過 Lync 2010 用戶端直接變更 Active Directory 網域服務設定檔中所使用的影像。 如果有的話，他們可以使用下列其中一個選項來執行此動作：

  - **Sharepoint server**   使用者可以在 sharepoint 伺服器上將相片上傳到「我的網站」，然後[設定 sharepoint 中的設定檔同步](http://go.microsoft.com/fwlink/p/?linkid=507466)處理，將相片同步處理到 Active Directory 網域服務中的**thumbnailPhoto**屬性。

  - **儲存在可公開存取的 URL**   的相片，使用者可以設定其使用者相片，指定要使用之影像的公開存取 url。 在沒有密碼的情況下，影像必須能夠公開存取。 儲存在指定網址的影像會透過目前狀態資訊的連絡人卡片類別傳送給其他使用者。 當 Lync 用戶端需要顯示使用者相片時，它會從指定的網址中檢索影像。

  - **Windows PowerShell**   系統管理員的 exchange 2010 Cmdlet 可以在 exchange 2010 管理 Shell 中執行[RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) Cmdlet，以管理**thumbnailPhoto**屬性。 在使用 Exchange 2010 Cmdlet 匯入影像時，檔案大小限制為 10 KB。

  - **協力廠商工具**   使用者只能將自己的相片上傳給**thumbnailPhoto**屬性。

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>從網址顯示圖片

當您選擇 [**從網址顯示圖片**] 選項時，Lync 會在您輸入的位址中取得圖像，並在 Lync 中針對您的使用者相片顯示該影像。

使用網址中的圖像的考慮事項包括下列各項：

  - 檔案大小限制是由用戶端原則中使用[CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) Cmdlet 定義的**MaxPhotoSizeKB**屬性所決定。 預設大小限制為 30 KB。 最大值為 100 KB。 圖像的解析度沒有限制，但如果您嘗試使用超過大小限制的圖像檔案，則不會將其下載至 Lync 用戶端。 您可以將此值設定為0，以停用 Lync 中的所有使用者相片。

  - 外部同盟連絡人可以看到來自網址的使用者相片。

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>使用用戶端原則 Cmdlet 管理使用者的相片

在 Lync Server 2010 中，用戶端原則設定是使用 CsClientPolicy Cmdlet 進行設定。 設定的原則設定會透過頻帶內設定傳送至用戶端。 判斷使用者相片體驗的 CsClientPolicy Cmdlet 的兩個參數是**DisplayPhoto**和**MaxPhotoSizeKB**。 **DisplayPhoto**和**MaxPhotoSizeKB**的對應內建提供參數已命名為**PhotoUsage**。 **PhotoUsage**參數的值會透過**endpointConfiguration** **provisionGroup**傳送給用戶端。 如需詳細資訊，請參閱[用戶端原則與設定的概覽](http://go.microsoft.com/fwlink/?linkid=507470)。

**DisplayPhoto**參數值決定使用者相片影像的來源。 下表包含支援的值。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DisplayPhoto 參數值</th>
<th>影像來源</th>
<th>Lync 2010 用戶端設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>所有</p></td>
<td><p><strong>不要顯示我的圖片</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>預設的公司圖片</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>網址</p></td>
<td><p><strong>從網址顯示圖片</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Lync 2010 用戶端如何取得相片

在 Lync 2010 中，使用者相片是透過通訊錄服務在伺服器上管理。 Lync 用戶端會先查詢伺服器上的通訊錄網頁查詢（ABWQ）服務（透過通訊組展開 Web 服務公開），以取得使用者相片。 用戶端會收到映射檔，然後將它複製到使用者的快取，以避免在每次需要顯示圖像時下載影像。 從查詢傳回的屬性值也會儲存在使用者的快取通訊錄服務專案中。 通訊錄服務每24小時都會刪除所有快取的影像，這表示在伺服器上的快取中，新的使用者影像可能需要長達24小時才能更新。 您可以使用[CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) Cmdlet 強制更新快取。

目前狀態中包含的使用者相片也有一個相關聯的雜湊值，由 Lync 用戶端用來判斷是否有可用的較新影像。 用戶端會在目前狀態中使用的影像檔案自動收到變更通知。

<div class=" ">


> [!NOTE]  
> 因為相片未儲存在 GalContacts 資料庫中，所以下載使用者相片並不依賴于用戶端原則中的<STRONG>AddressBookAvailability</STRONG>設定（<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>）。



</div>

ABWQ 服務的查詢包含下列屬性：

  - **PhotoHash**   二進位相片資料的雜湊值，並使用它來判斷目前的相片是否已變更。

  - **PhotoRelPath**   儲存在伺服器上的圖像檔案相對路徑。

  - **PhotoSize**   圖像檔案的大小（以位元組為單位）。

  - **TimeStamp**   上次從伺服器下載圖像檔案並複製到用戶端快取的日期和時間。

接著，Lync 2010 用戶端在取得圖像檔案之後，會將從查詢所傳回的屬性值與用戶端從區段內的配置中接收的屬性值進行比較，以查看它們是否不同。 如果值不同，用戶端會使用 HTTP 取得請求來檢索登入使用者的圖像檔案。

此外，用戶端會在每24小時從已建立圖像檔案的快取時間，並與用戶端上的值比較伺服器上的**PhotoHash**屬性值。 如果值不同，用戶端會知道圖像檔案已變更。 若要取得更新的圖像檔案，用戶端會重新查詢 ABWQ 服務，以更新用戶端快取中的映射檔與伺服器上的映射檔，也就是在用戶端快取中重設檔案上的**時間戳記**。

下列是 ABWQ 服務查詢的範例回應：
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Lync 2013 中的使用者相片

Lync 2013 為使用者相片推出高解析度影像的支援。 Lync 2013 也提供支援，可將使用者相片儲存在 Exchange 2013 上的使用者信箱中，這會移除 Lync 2010 中存在的影像解析度和大小限制。 在 Lync 2013 中的使用者相片，最多可有648圖元的648圖元，檔案大小最大為 20 MB。 Lync 2013 中的高解析度相片必須位於 Exchange 2013 的使用者信箱中，而且只有 Lync 2013 用戶端支援。 這項與 Exchange 的整合會利用2013版本的 Lync、Exchange 和 SharePoint 中所包含的新授權架構（即「Oauth」）。

如果 Exchange 2013 未在您的部署中使用，則對使用者相片的支援與 Lync 2010 完全相同。 不過，在 Lync 2013 用戶端中選擇要使用的相片的使用者選項會有所不同。 在 Lync 2013 用戶端中，使用者可以選取 [**隱藏我的圖片**] 或 [**顯示我的圖片**]。 預設不提供**從網站顯示圖片**的選項，但可以指派用戶端原則來啟用。

<div>

## <a name="hide-my-picture"></a>隱藏我的圖片

使用者相片的設定在 Lync 2013 的 [**選項**] 對話方塊中。 當您選擇 [**隱藏我的圖片**] 時，系統不會針對您的 lync 用戶端顯示任何使用者相片，但您的相片仍會顯示在您的連絡人卡片上，且在 lync 以外。

</div>

<div>

## <a name="show-my-picture"></a>顯示我的圖片

當您選擇 [**顯示我的圖片**] 選項時，您的使用者相片會顯示在您的 lync 用戶端，以及 lync 交談中的其他使用者。 所使用的圖像是儲存在 AD DS 中的影像。

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>顯示網站上的圖片

在用戶端原則設定為啟用之後，Lync 2013 中就會提供 [**從網站顯示圖片**] 選項。 用戶端版本必須比15.0.4535.1002 安裝的版本必須更新，且與[Lync 累積更新：2013年11月](http://go.microsoft.com/fwlink/p/?linkid=509908)。 使用者可能需要登出後再重新登入，以查看用戶端中的變更。

您可以在 Lync Server 管理命令介面中執行 [[設定 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)原則]，將用戶端原則設定為 [啟用] 以**顯示來自網站**設定的圖片。 下列範例 Cmdlet 示範如何針對您部署中的所有使用者全域設定原則：

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


當圖像上傳到使用者的信箱時，Exchange 會自動建立可在用戶端應用程式中使用的影像較低解析度版本。 使用者相片也會在 AD DS 中更新。

<div class=" ">


> [!NOTE]  
> 在 AD DS 中更新影像檔案時，會建立 48 x 48 圖元的影像，並用於 AD DS 中的 thumbnailPhoto。 任何現有的圖像都會被取代。 因此，如果您已將 96 x 96 影像新增到 AD DS，就會使用新的 48 x 48 影像來覆寫它。 這只是重要的一點，就是您在您的環境中擁有 Lync 2010 用戶端的使用者，因為這些用戶端會從 AD DS 取得使用者相片。 如果您的組織中有 Lync 2010 用戶端，您可以匯入 96 x 96 圖元影像，以取代 AD DS 所建立的圖像。



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Lync 2013 中的使用者相片支援

在 Lync 2013 中，使用者相片支援三種影像解析度，如下表所述。 所使用的影像是由指派給 Lync 使用者的用戶端原則設定所決定。 如需詳細資訊，請參閱本主題中的 [使用用戶端策略 Cmdlet 管理使用者的相片]。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>圖像解析度（圖元）</th>
<th>應用程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>如果沒有選取較高的解析度圖像，就會使用</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>在 Outlook Web App 和 Outlook 2013 中使用</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>在 Lync 2013 桌面用戶端和 Lync 2013 Web App 中使用</p></td>
</tr>
</tbody>
</table>


任何在 Exchange 2013 中啟用信箱的使用者，都可以透過 Outlook Web Access 或 Lync 2013 用戶端選項上傳不同的影像，包括高解析度相片。 使用的影像建議設定包括：

  - **圖像解析度**   648 乘以648圖元

  - **色深**   24 位

  - **影像檔案大小**   最大為 20 MB

  - **JPEG 檔案格式**   

648圖元乘648圖元的典型24位 JPEG 影像的檔案大小為大約 240 KB，所以每4個使用者相片都需要 1 MB 的儲存空間。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

