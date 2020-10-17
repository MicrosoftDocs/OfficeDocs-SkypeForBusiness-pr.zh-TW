---
title: 設定立即訊息 (IM) 的檔案傳送和 URL 篩選
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bad134c770300820bd4fb6bd2d72e648b5f34777
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517510"
---
# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

智慧 IM 篩選工具可協助保護您的 Lync Server 2013 部署，使其免受最常見的病毒形式傳播，以降低使用者體驗的程度。 使用智慧型 IM 篩選器可以設定篩選器，以封鎖來自企業防火牆外部之不明端點的來路不明或潛在有害的立即訊息。 您可以指定用來判斷所應封鎖項目的條件，藉以設定篩選器，例如立即訊息中包含具有特定首碼的超連結與具有特定副檔名的檔案。

智慧型 IM 篩選器提供下列功能：

  - 增強型 URL 篩選。

  - 增強型檔案傳輸篩選。

智慧型 IM 篩選器的設定包括：

  - 設定 URL 篩選。

  - 設定檔案傳輸篩選。

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>篩選選項套用至立即訊息的方式

在您部署智慧 IM 郵件篩選工具之前，您必須瞭解如何套用篩選選項，因為郵件是從一部 Lync Server 2013 伺服器路由傳送到另一個。 無論伺服器位於單一組織內，或是涵蓋多個組織，套用這些篩選選項的方式是一樣的。 這種一致性適用於自訂通知和警告文字插入訊息及跨伺服器傳送的方式。

<div>


> [!NOTE]
> 立即訊息篩選器會增加訊息中處理 URL 所需的 CPU 資源量。 此增加的 CPU 需求也會影響 Lync Server 的效能。



</div>

使用 [Lync Server 控制台] 中 [ **IM 和目前狀態**] 群組中的 [ **URL 篩選**] 頁面，您可以封鎖部分或所有超連結或設定警告。 當您選擇 [超連結首碼]**** 選項 [傳送警告訊息]**** 時，即會在包含超連結的立即訊息開頭處插入警告。

當立即訊息從一部伺服器傳送到另一部伺服器時，會套用下列一般方針：

  - 如果伺服器封鎖立即訊息 (由於您在 **[URL 篩選器]** 頁面上選取了 **[封鎖含有副檔名的 URL]** 核取方塊，或選擇了 **[超連結首碼]** 選項 **[封鎖超連結]**)，則會將錯誤訊息傳回至用戶端。後續的伺服器將不會收到此立即訊息。

  - 如果伺服器 (Server1) 將警告新增至包含作用中超連結的立即訊息中，收到此立即訊息的後續伺服器 (Server2) 仍可以依據該立即訊息中出現的這個作用中超連結來採取不同的動作，並封鎖該立即訊息或新增警告。如果 Server2 設定為僅新增此 URL 的警告，便會移除之前由 Server1 新增的警告，而在 Server2 上所設定的警告將會新增至該立即訊息的開頭處。

<div>


> [!NOTE]
> 如果您是在混合環境中執行 Lync Server 2013，則使用智慧 IM 篩選應用程式所需的即時通訊伺服器2005（含 SP1）是最低的版本。 不具 SP1 的 Live Communications Server 2005 不支援智慧型 IM 篩選器。



</div>

<div>

## <a name="url-filtering"></a>URL 篩選

URL 可根據其超連結首碼受到篩選。以下是有效首碼的範例：

  - www \* 。

  - Ftp。

  - HTTP.sys

如果您未設定立即訊息篩選器來執行任何 URL 篩選，則立即訊息中所包含的所有 URL 都會以原狀通過伺服器。如果您設定立即訊息篩選器來執行 URL 篩選，則立即訊息中的 URL 都會根據您在 **[編輯 URL 篩選器]** 或 **[新增 URL 篩選器]** 對話方塊中所選取的選項受到篩選。

  - **啟用 URL 篩選器**    此選項會為全域部署或您所選取的網站啟用 URL 篩選。

  - **使用副檔名**     封鎖 URLs立即訊息篩選器會封鎖任何使用中的內部網路或網際網路 URL，其中包含副檔名列于 [**編輯檔案篩選**] 對話方塊的 [**檔案類型副檔名**] 底下的副檔名。 當封鎖 URL 時，系統會向寄件者顯示錯誤訊息。 選取此選項時，此選項會優先于所有其他篩選選項，以 [副檔名] 副檔名為 [ **封鎖**] 的任何副檔名。
    
    <div>
    

    > [!IMPORTANT]
    > 副檔名的篩選僅限於標準的檔案名稱。內嵌在其他名稱中的副檔名可能篩選不出來。

    
    </div>

若要設定如何處理立即訊息交談中的超連結，請選取下列位於 [超連結首碼]**** 下方的其中一個選項：

  - 不**篩選**    在郵件中 URLs 會透過伺服器傳送。 當您選擇此選項時，會出現 [ **允許] 消息** 框。 在 [ **允許消息** ] 方塊中，指定您要在每個包含超連結的立即訊息開頭插入的通知。 此通知包含的字元不得超過65535個。

  - **封鎖超連結**    傳送包含作用中超連結的立即訊息會由 Lync Server 封鎖，並對寄件者顯示錯誤訊息。

  - **傳送警告訊息**    Lync Server 允許立即訊息中的使用中超連結，但包含警告。 選擇此選項時，會出現 [警告訊息]**** 方塊。 在 [警告訊息]**** 方塊中，您必須輸入要在包含有效超連結的立即訊息中隨附的警告。 例如，此警告可指出點選不明連結的潛在風險，或提及您組織的相關原則與需求。 此警告最多可包含 65535 個字元。

選取 **[封鎖超連結]** 或 **[傳送警告訊息]** 時，可用的選項如下：

  - **排除本機內部網路超連結**    立即訊息篩選只會封鎖網際網路 URLs。 內部網路內位置的 URLs 會透過伺服器進行未修改的傳遞。 不過，內部網路 URLs 執行 Lync Server 的個別伺服器，取決於哪些類型的本機網站會被視為其內部網路區域的一部分。 若要檢查伺服器的內部網路區域設定，請參閱在 [Lync server 2013 中修改預設 URL 篩選器](lync-server-2013-modify-the-default-url-filter.md)中的「在 Internet Explorer 中設定您的內部網路設定」程式。

  - **篩選這些超連結首碼**    若要選擇要封鎖的首碼，請按一下 [**選取**]，然後在 [**選取超連結首碼**] 中，將首碼新增至 [**超連結首碼**] 清單。
    
    除了 **href** 以外的所有首碼都必須以點或冒號結尾，或是以星號接著點為結尾。 有效的首碼可以包含有效 URL 字元集合中的任何字元，星號 (\*) 除外。 有效的 URL 字元組為： \# \* +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ \_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>檔案傳輸篩選

檔案傳輸篩選對立即訊息與會議都會有影響。對於會議，這些設定會影響 Office Live Meeting 2007 用戶端中的講義功能及多媒體播放功能。

<div>


> [!NOTE]
> Lync Server 也提供檔案傳輸設定選項。 除了 Lync Server 中可用的用戶端控制項之外，也提供此伺服器端選項。



</div>

當您在 Office Live Meeting 2007 用戶端中使用講義功能，或使用各種檔案類型的多媒體播放功能時，您可以篩選立即訊息交談期間的檔案傳輸。您可以設定下列選項以控制檔案傳輸：

  - **啟用檔案篩選器**    此選項會為全域部署或您所選取的網站啟用檔篩選。
    
    當您啟用檔案篩選器時，您可以在 **[檔案傳輸]** 中選擇下列其中一個選項：
    
      - **封鎖特定檔案類型**    您可以指定要封鎖的副檔名清單，以指定由伺服器篩選的檔案傳輸要求。 清單中的專案可以包含所有標準字元，但不能包含萬用字元 (\*) 。 在 Office Live Meeting 2007 用戶端中，講義功能已啟用，但無法上傳或下載任何具有此副檔名的檔案。 如果您選取 [ **Url 篩選**] 索引標籤上所列之 url 篩選器之設定上的 [**封鎖 URLs 搭配副檔名**] 核取方塊，則 url 篩選會使用此相同清單來封鎖包含這些副檔名的使用中超連結。 若要選擇要封鎖的檔案類型，請按一下 [ **選取**]，然後在 [ **選取檔案類型**] 中，將檔案類型副檔名新增至 [選取的 **檔案類型副檔名** ] 清單。
    
      - **全部封鎖**    伺服器會丟棄所有包含檔案傳輸要求的立即訊息，並將錯誤訊息傳回給要求的寄件者。 Office Live Meeting 2007 用戶端中的講義功能已停用。

<div>


> [!IMPORTANT]
> 副檔名的篩選僅限於標準的檔案名稱。內嵌在其他名稱中的副檔名可能篩選不出來。



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中修改預設檔案傳輸篩選器](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [在 Lync Server 2013 中為特定網站建立新的檔案傳輸篩選器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [在 Lync Server 2013 中修改預設 URL 篩選器](lync-server-2013-modify-the-default-url-filter.md)

  - [在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中管理 IM 及顯示狀態設定](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

