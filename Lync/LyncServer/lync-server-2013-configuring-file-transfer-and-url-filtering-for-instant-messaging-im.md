---
title: 針對立即訊息（IM）設定檔案傳輸與 URL 篩選
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>在 Lync Server 2013 中設定立即訊息（IM）的檔案傳輸與 URL 篩選

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

智慧 IM 篩選工具可協助保護您的 Lync Server 2013 部署，避免受到最常見的病毒傳播，以及最小限度地降低使用者體驗。 使用智慧 IM 篩選來設定篩選器，以封鎖來自公司防火牆以外的來自未知端點的未經請求或可能有害的立即訊息。 您可以透過指定準則來決定要封鎖哪些專案（例如包含特定首碼的超連結，以及具有特定副檔名的檔案），來設定篩選。

智慧 IM 篩選提供下列功能：

  - 增強的 URL 篩選。

  - 增強的檔案傳輸篩選。

設定智慧 IM 篩選包括下列各項：

  - 設定 URL 篩選。

  - 配置檔案傳輸篩選。

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>如何將篩選選項套用至立即訊息

在您部署智慧 IM 訊息篩選工具之前，您必須瞭解如何套用篩選選項，因為郵件是從一個 Lync Server 2013 伺服器路由到另一個。 套用這些篩選選項的方式是一致的，不論伺服器是位於單一組織中，還是跨組織界限。 此一致性會套用至將自訂通知與警告文字插入郵件中並在伺服器之間傳送的方式。

<div>


> [!NOTE]
> [立即訊息] 篩選會增加處理郵件中的 Url 所需的 CPU 資源量。 這種 CPU 需求增加也會影響 Lync Server 的效能。



</div>

透過使用 [Lync Server 控制台] 中的 [ **IM 和目前狀態**] 群組中的 [ **URL 篩選**] 頁面，您可以封鎖部分或所有的超連結，或設定警告。 當您選擇 [**超連結首碼**] 選項 [**傳送警告訊息**] 時，會在包含超連結的立即訊息開頭插入警告。

當立即訊息從一個伺服器傳送到另一個伺服器時，請遵循下列一般指導方針：

  - 如果伺服器封鎖立即訊息（因為您在 [ **URL 篩選**] 頁面上選取了 [**以檔案副檔名封鎖 url** ] 核取方塊，或是因為您選擇的是 [**超連結首碼**] 選項**區塊超連結**），則會傳回錯誤訊息給用戶端。 後續伺服器不會收到這則立即訊息。

  - 如果伺服器（Server1）在包含作用中超連結的立即訊息中新增警告，則在立即訊息中出現的後續伺服器（Server2）會根據此使用中的超連結，繼續進行其他動作並封鎖[立即訊息] 或 [新增警告]。 如果 Server2 只設定為針對此 URL 新增警告，則會移除 Server1 所新增的舊版警告，並將在 Server2 上設定的警告新增至立即訊息的開頭。

<div>


> [!NOTE]
> 如果您在混合式環境中執行 Lync Server 2013，則使用 [即時通訊伺服器 2005] 與 SP1 是使用智慧 IM 篩選應用程式所需的最低版本。 即時通訊伺服器2005不支援智慧 IM 篩選器（沒有 SP1）。



</div>

<div>

## <a name="url-filtering"></a>URL 篩選

Url 會根據其超連結首碼篩選。 下列範例是有效的首碼：

  - www\*。

  - ftp.

  - HTTP

如果您沒有設定立即訊息篩選來執行任何 URL 篩選，立即訊息中包含的所有 Url 都會透過伺服器進行未修改的傳送。 如果您設定立即訊息篩選來執行 URL 篩選，立即訊息中的 Url 會根據您在 [**編輯 URL 篩選**] 或 [**新增 url 篩選**] 對話方塊中選取的選項進行篩選。

  - **啟用 url 篩選**   ：此選項可為全域部署或您選取的網站啟用 URL 篩選。

  - **使用副檔名**   來封鎖 url：立即訊息篩選會封鎖任何作用中的內部網路 intranet 或網際網路 URL，其中包含的副檔名會列在 [編輯檔案**篩選器**] 對話方塊中的 [檔案**類型延伸**] 底下。 當 URL 被封鎖時，寄件者會顯示錯誤訊息。 選取此選項時，此選項優先于**將 [檔案類型延伸**] 下所定義之任何副檔名的所有其他篩選選項。
    
    <div>
    

    > [!IMPORTANT]
    > 檔案延伸的篩選只能是標準的檔案名。 篩選可能無法搭配內嵌在其他名稱中的副檔名。

    
    </div>

若要設定在立即訊息交談中處理超連結的方式，請在 [**超連結前置**詞] 下，選取下列其中一個選項：

  - **請勿**   在郵件中篩選 url 會透過伺服器傳送。 當您選擇此選項時，會出現 [**允許] 消息**框。 在 [**允許訊息**] 方塊中，指定您要在包含超連結的每一條立即訊息開頭插入的通知。 此通知可包含的字元不超過65535個。

  - **[封鎖超連結**   ]：由 Lync Server 封鎖包含活動超連結的立即訊息，且寄件者會顯示錯誤訊息。

  - **傳送警告訊息**   Lync Server 允許立即訊息中的活動超連結，但包含警告。 當您選擇此選項時，會出現**警告訊息**。 在 [**警告訊息**] 方塊中，您必須輸入您想要在包含有效超連結的立即訊息中包含的警告。 例如，此警告可能會顯示按一下未知連結的潛在危險，或者可能會參照貴組織的相關原則與需求。 警告不能超過65535個字元。

如果您選取 [**封鎖超連結**] 或 [**傳送警告訊息**]，就可以使用下列選項：

  - **排除本機內部網路超連結**   [立即訊息篩選] 只會封鎖網際網路 url。 內部網路中的位置 Url 會透過伺服器進行未修改的傳送。 不過，個別伺服器執行 Lync Server 所需的 intranet Url，取決於哪些類型的本機網站被視為其內部網路區域的一部分。 若要檢查伺服器的 intranet 區域設定，請參閱在[Lync server 2013 中修改預設 URL 篩選器](lync-server-2013-modify-the-default-url-filter.md)中的「在 Internet Explorer 中設定 intranet 設定」程式。

  - **篩選這些超連結首碼**   若要選擇要封鎖的首碼，請按一下 [**選取**]，然後在 [**選取超連結首碼**] 中，將 [首碼] 新增到 [**超連結首碼**] 清單中。
    
    **Href**以外的所有首碼，都必須以句號或冒號結尾，或是星號接著是句號。 有效的首碼可以包含一組有效 URL 字元（星號（\*）除外）中的任何字元。 有效的 URL 字元集合\# \*為： +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^\_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>檔案傳輸篩選

篩選轉移篩選會影響立即訊息和會議。 在會議中，這些設定會影響 Office Live Meeting 2007 用戶端和多媒體播放功能中的講義功能。

<div>


> [!NOTE]
> Lync Server 也提供檔案傳輸設定選項。 除了 Lync Server 中提供的用戶端控制項之外，還提供此伺服器端選項。



</div>

當您使用 Office Live Meeting 2007 用戶端中的講義功能，以及適用于所有檔案類型的多媒體播放功能時，您可以在立即訊息交談期間篩選檔案傳輸。 您可以設定下列選項來控制檔案傳輸：

  - **[啟用檔案篩選**   ]：此選項可為全域部署或您選取的網站啟用檔案篩選。
    
    當您啟用檔案篩選器時，您可以在 [檔案**傳輸**] 中選擇下列其中一個選項：
    
      - **封鎖特定檔案類型**   ：指定要封鎖的檔副檔名清單，以指定哪些檔案傳輸要求會受到伺服器篩選。 清單中的專案可以包含所有標準字元，但不能包含通配字元\*（）。 在 Office Live Meeting 2007 用戶端中，講義功能已啟用，但無法上傳或下載具有此副檔名的任何檔案。 如果您在 [ **Url 篩選**] 索引標籤上所列的 url 篩選的設定中選取 [**封鎖含檔案副檔名的 url** ] 核取方塊，url 篩選就會使用相同的清單來封鎖包含這些副檔名的作用中超連結。 若要選擇要封鎖的檔案類型，請按一下 [**選取**]，然後在 [**選取檔案類型**] 中，將檔案類型副檔名新增到 [選取的**檔案類型副檔名**] 清單中。
    
      - **[封鎖所有**   伺服器]：除去所有包含檔案傳輸要求的立即訊息，並傳回錯誤訊息給要求的寄件者。 Office Live Meeting 2007 用戶端中的 [講義] 功能已停用。

<div>


> [!IMPORTANT]
> 檔案延伸的篩選只能是標準的檔案名。 篩選可能無法搭配內嵌在其他名稱中的副檔名。



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中修改預設的檔案傳輸篩選器](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [針對特定網站在 Lync Server 2013 中建立新的檔案傳輸篩選器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [在 Lync Server 2013 中修改預設的 URL 篩選](lync-server-2013-modify-the-default-url-filter.md)

  - [在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中管理 IM 及顯示狀態設定](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

