---
title: Lync 中使用者相片的顯示方式
description: Lync 中使用者相片的顯示方式。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12ea9e19b3965994c025659f1b2249c49ec32a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551109"
---
# <a name="how-user-photos-are-displayed-in-lync"></a>Lync 中使用者相片的顯示方式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-25_

**摘要：** 顯示在 Lync 用戶端中的使用者相片可能會因您使用哪個 Lync 功能而異，例如會議或 IM 交談。

Lync 2010 引進的功能可加入具有 Lync 設定檔的相片，以顯示給其他 Lync 使用者。 您也可以選擇是否要在 Lync 用戶端中為您的連絡人顯示照片。 在 Lync 2013 中，支援高解析度的相片的使用者。 本主題說明 Lync 用戶端如何取得及顯示使用者相片、儲存影像的位置、每個影像來源的限制，以及不同 Lync 服務使用使用者相片的方式。

<div>

## <a name="planning-considerations"></a>規劃考量

當您規劃對使用者相片的支援時，應考慮下列事項。

  - 高定義使用者相片支援要求使用者的信箱位於 Exchange 2013，而 Lync 使用者帳戶位於 Lync 2013 集區。

  - 只有在使用 Lync Server 2013 和 Exchange 2013 的環境中，才支援高定義使用者相片。

  - 信箱在 Exchange 2010 上的使用者，將永遠使用來自 AD DS 的 **thumbnailPhoto** 屬性做為使用者相片的來源。

  - 從 AD DS 儲存為 **thumbnailPhoto** 屬性的使用者相片不會顯示在外部/同盟連絡人。

  - 如果使用者連絡人的相片儲存在 AD DS 中，則所使用的圖像檔案限制為96×96圖元，且不得超過 100 KB 的檔案大小。

  - 如果 Lync Server 與 Exchange Server 之間的連線已遺失，將會顯示使用者的低解析度 **thumbnailPhoto** ，並只會顯示給內部使用者。

  - 當使用中的音箱未啟用影片時，會在 Lync 2013 會議中顯示高解析度的使用者相片。 此外，將滑鼠移到圖庫中的縮圖照片上方，會顯示高解析度的相片。

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Lync 2010 中的使用者相片

在 Lync 2010 用戶端中，您可以從兩個選項中選擇顯示設定檔的相片、 **預設的公司圖片** 及 **顯示網址中的圖片**。

<div>

## <a name="default-corporate-picture"></a>預設公司圖片

當您選擇 [ **預設公司圖片** ] 選項時，Lync 會從 Active Directory 網域服務中取得為您顯示的相片。 使用的影像是定義為 Active Directory 網域服務中 **thumbnailPhoto** 屬性值的影像。 這是 Exchange 在 Outlook 中顯示圖像時所使用的相同檔案。

使用 Active Directory 網域服務中的影像的考慮包括下列各項：

  - 只支援最高96圖元至96圖元的影像。 影像的檔案大小限制為 100 KB。

  - 根據預設，使用者可以變更用於 **thumbnailPhoto** 屬性的影像，但不能直接透過 Lync 用戶端進行。 您可以透過 Active Directory 網域服務停用此。

  - 儲存在 Active Directory 網域服務中的圖像不會顯示給組織外部的連絡人，即使他們是同盟連絡人也是一樣。

  - 在大型組織中，儲存及檢索大量使用者的影像可能會影響 Active Directory 網域服務資料庫的大小和效能。

  - 有限的影像尺寸及檔案大小表示只可使用低解析度圖像。

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>使用者如何在 Active Directory 網域服務中管理使用者相片

使用者無法直接透過 Lync 2010 用戶端變更其 Active Directory 網域服務設定檔中所使用的影像。 他們可以使用下列其中一個選項來執行（如果有的話）：

  - **SharePoint 伺服器**    使用者可以將相片上傳至「我的網站」的 SharePoint 伺服器上，然後[在 SharePoint 中設定設定檔同步](https://go.microsoft.com/fwlink/p/?linkid=507466)處理，以同步處理相片至 Active Directory 網域服務中的**thumbnailPhoto**屬性。

  - **儲存在可公開存取的 URL**     上的相片使用者可以設定其使用者相片，指定要使用之影像的公開存取 URL。 在沒有密碼的情況下，必須可公開存取影像。 儲存在指定網址的圖像會透過狀態資訊中的連絡人卡片類別轉接給其他使用者。 當 Lync 用戶端需要顯示使用者相片時，它會從指定的網址檢索圖像。

  - **Windows PowerShell**     的 Exchange 2010 Cmdlet管理員可以在 Exchange 2010 管理命令介面中執行[Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) Cmdlet，以管理**thumbnailPhoto**屬性。 當圖像匯入 Exchange 2010 Cmdlet 時，檔案大小限制為 10 KB。

  - **協力廠商工具**    使用者只能將自己的相片上傳至**thumbnailPhoto**屬性。

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>顯示網址中的圖片

當您選擇 [ **顯示網址中的圖片** ] 選項時，lync 會在您所輸入的位址取得影像，並在 Lync 中為您的使用者相片顯示此圖像。

使用網址中的圖像的考慮包括下列各項：

  - 檔案大小限制是由用戶端原則中使用[New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) Cmdlet 所定義的**MaxPhotoSizeKB**屬性所決定。 預設大小限制為 30 KB。 最大值為 100 KB。 對影像的解析度沒有任何限制，但如果您嘗試使用超過大小限制的圖像檔案，則不會將其下載至 Lync 用戶端。 您可以將值設為0，以停用 Lync 中的所有使用者相片。

  - 來自網址的使用者相片可由外部同盟連絡人看到。

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>使用用戶端原則 Cmdlet 來管理使用者相片

在 Lync Server 2010 中，用戶端原則設定會以 CsClientPolicy Cmdlet 進行設定。 設定的原則設定會透過帶內布建來傳送給用戶端。 CsClientPolicy Cmdlet 的兩個參數，可判斷使用者的照片體驗 **DisplayPhoto** 和 **MaxPhotoSizeKB**。 對應 **DisplayPhoto** 和 **MaxPhotoSizeKB** 的內帶內布布建參數稱為 **PhotoUsage**。 **PhotoUsage**參數的值會透過**endpointConfiguration** **provisionGroup**傳送給用戶端。 如需詳細資訊，請參閱 [用戶端原則和設定的概述](https://go.microsoft.com/fwlink/?linkid=507470) 。

**DisplayPhoto**參數值會決定使用者相片影像的來源。 下表包含支援的值。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DisplayPhoto 參數值</th>
<th>圖像來源</th>
<th>Lync 2010 用戶端設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>無</p></td>
<td><p><strong>不要顯示我的圖片</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>預設公司圖片</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>網址</p></td>
<td><p><strong>顯示網址中的圖片</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Lync 2010 用戶端如何取得相片

在 Lync 2010 中，使用者相片是透過通訊錄服務在伺服器上管理。 Lync 用戶端會先查詢伺服器上的通訊錄 Web 查詢 (ABWQ) 服務（透過通訊群組清單擴充 Web 服務公開），以取得使用者照片。 用戶端會接收圖像檔案，然後將它複製到使用者的快取，以避免每次需要顯示圖像時進行下載。 從查詢傳回的屬性值也會儲存在使用者的快取通訊錄服務專案中。 通訊錄服務每24小時就會刪除所有快取的影像，這表示在伺服器的快取中，新使用者影像的更新最多可能需要24小時。 您可以使用 [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) Cmdlet 強制更新快取。

「目前狀態」中包含的使用者相片也有一個相關聯的雜湊值，Lync 用戶端使用該雜湊值來判斷是否有更新的影像可用。 用戶端會自動向顯示狀態中所用之圖像檔案的變更通知。

<div class=" ">


> [!NOTE]  
> 因為相片未儲存在 GalContacts 資料庫中，所以下載使用者相片與用戶端原則 (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>) 上的<STRONG>AddressBookAvailability</STRONG>設定無關。



</div>

ABWQ 服務的查詢包含下列屬性：

  - **PhotoHash**    二進位照片資料的雜湊值，可用來判斷目前的相片是否已變更。

  - **PhotoRelPath**    儲存在伺服器上之圖像檔案的相對路徑。

  - **PhotoSize**    圖像檔案的大小（以位元組為單位）。

  - **TimeStamp**    從伺服器上最後下載圖像檔案，並將其複製到用戶端快取的日期和時間。

接下來，在檢索影像檔之後，Lync 2010 用戶端會將從查詢所傳回的屬性值與用戶端從頻帶所接收的屬性值進行比較，以查看兩者是否不同。 如果這些值不同，用戶端會使用 HTTP GET 要求來檢索已登入使用者的影像檔。

此外，用戶端會每隔24小時從該伺服器的快取版本所建立的時間，與用戶端上的值進行比較，以比較伺服器上的 **PhotoHash** 屬性值。 如果值不同，用戶端就會知道圖像檔已變更。 若要取得更新的映射檔，用戶端會重新查詢 ABWQ 服務，以使用伺服器上的映射檔更新用戶端快取中的映射檔，也就是在用戶端快取中重設檔上的 **時間戳記** 。

以下是對 ABWQ 服務的查詢回應範例：
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

Lync 2013 為使用者相片引進高解析度影像的支援。 Lync 2013 也包含支援在 Exchange 2013 上的使用者信箱中儲存使用者相片，這會移除 Lync 2010 中所提供的影像解析度和大小限制。 Lync 2013 中的使用者相片可以是最高648圖元的648圖元，檔案大小最高為 20 MB。 Lync 2013 中的高解析度相片必須位於 Exchange 2013 的使用者信箱中，而且只支援 Lync 2013 用戶端。 這種與 Exchange 的整合利用2013版本的 Lync、Exchange 及 SharePoint 稱為 Oauth 所包含的新授權架構。

如果部署中未使用 Exchange 2013，則對使用者相片的支援與 Lync 2010 相同。 不過，在 Lync 2013 用戶端中，選擇要使用的相片的使用者選項是不同的。 在 Lync 2013 用戶端中，使用者可以選擇 [ **隱藏我的圖片** ] 或 [ **顯示我的圖片**]。 預設不提供 **從網站顯示圖片** 的選項，但可透過指派用戶端原則來啟用。

<div>

## <a name="hide-my-picture"></a>隱藏我的圖片

使用者相片的設定是在 Lync 2013 的 [ **選項** ] 對話方塊中。 當您選擇 [ **隱藏我的圖片**] 時，不會在 lync 用戶端中為您顯示任何使用者相片，但您的相片仍會顯示在連絡人卡片上和 Lync 以外的地方。

</div>

<div>

## <a name="show-my-picture"></a>顯示我的圖片

當您選擇 [ **顯示我的圖片** ] 選項時，您的使用者相片會顯示在您的 lync 用戶端，以及 lync 交談中的其他使用者。 使用的圖像是儲存在 AD DS 中的圖像。

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>顯示網站中的圖片

在設定了用戶端原則加以啟用之後，Lync 2013 中的 [ **顯示來自網站的圖片** ] 選項便可供使用。 用戶端版本必須比15.0.4535.1002 （隨 [Lync 累積更新安裝）：2013年11月](https://go.microsoft.com/fwlink/p/?linkid=509908)更新。 使用者可能需要登出後再重新登入，以查看用戶端中的變更。

您可以在 Lync Server 管理命令介面中執行[Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)原則，將用戶端原則設定為啟用**從網站設定來顯示圖片**。 下列 Cmdlet 範例會示範如何針對您部署中的所有使用者，全域設定原則：

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


當圖像上傳至使用者的信箱時，Exchange 會自動建立可用於用戶端應用程式的較低解析度版本的影像。 使用者相片也會在 AD DS 中更新。

<div class=" ">


> [!NOTE]  
> 在 AD DS 中更新映射檔時，會在 AD DS 中為 thumbnailPhoto 建立並使用 48 x 48 圖元影像。 任何現有的圖像都會取代。 因此，如果您已將 96 x 96 圖像新增至 AD DS，它會以新的 48 x 48 影像覆寫。 這只是重要的一點，就是您在環境中使用 Lync 2010 用戶端，因為這些用戶端會從 AD DS 取得使用者相片。 如果您的組織中有 Lync 2010 用戶端，您可以匯入 96 x 96 圖元影像以取代 AD DS 所建立的影像。



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Lync 2013 中的使用者相片支援

在 Lync 2013 中，使用者照片支援三種影像解析度，如下表所述。 所使用的映射是由指派給 Lync 使用者的用戶端原則設定所決定。 如需詳細資訊，請參閱本主題中的「管理使用者的相片使用用戶端原則 Cmdlet」。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>圖像解析度 (圖元) </th>
<th>應用程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>如果沒有選取更高的解析度影像，則使用</p></td>
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


任何在 Exchange 2013 中啟用信箱的使用者，都可以透過 Outlook Web Access 或 Lync 2013 用戶端選項上傳不同的影像，包括高解析度照片。 使用的影像建議設定包括：

  - **影像解析度**    648 x 648 圖元

  - **色彩深度**    24位

  - **圖像檔案大小**    最多 20 MB

  - **檔案格式**    Jpeg

典型的24位 JPEG 圖像（648圖元 x 648 圖元）的檔案大小約為大約 240 KB，所以每四個使用者相片都需要 1 MB 的儲存空間。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

