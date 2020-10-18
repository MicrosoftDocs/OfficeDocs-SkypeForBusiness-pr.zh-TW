---
title: Lync Server 2013：手動建立或修改轉譯規則
description: Lync Server 2013：手動建立或修改轉譯規則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f393ca1983e072090cc27d47b142dace8b566c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574499"
---
# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>在 Lync Server 2013 中手動建立或修改轉譯規則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-06_

若要撰寫相符樣式及轉譯規則的規則運算式以定義轉譯規則，請遵循下列步驟。 或者，您也可以在 **組建轉譯規則** 工具中輸入一組值，並讓 Lync Server 控制台為您產生對應的符合模式和轉譯規則。 如需詳細資訊，請參閱 [使用 Lync Server 2013 中的組建轉譯規則工具建立或修改轉譯規則](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)。

<div>

## <a name="to-define-a-translation-rule-manually"></a>若要手動定義轉譯規則

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  若要開始定義轉譯規則，請遵循在 lync server 2013 中的「透過 [媒體旁路」設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md) 中的步驟，或在 [lync Server 2013 中設定](lync-server-2013-configure-a-trunk-without-media-bypass.md) 具有媒體旁路的主幹（透過步驟9）。

4.  在 **[新增轉譯規則]** 或 **[編輯轉譯規則]** 頁面的 **[名稱]** 欄位中，輸入可描述所轉譯號碼模式的名稱。

5.  (選用) 在 [描述]**** 中，輸入轉譯規則的描述，例如**美國國際長途撥號**。

6.  按一下 **[建置轉譯規則]** 區段底部的 **[編輯]**。

7.  在 [輸入規則運算式]**** 中輸入下列內容：
    
      - 在 [符合此模式]**** 中，指定用來比對要轉譯之號碼的模式。
    
      - 在 [轉譯規則]**** 中，指定轉譯號碼的格式模式。
    
    例如，如果您在**符合此模式**的情況下輸入** ^ \\ + (\\ d {9} \\ +) $** 和**轉譯規則**中的**011 $ 1** ，則此規則會將 + 441235551010 轉譯為011441235551010。

8.  按一下 ** [確定]** 儲存轉譯規則。

9.  按一下 ** [確定]** 儲存主幹組態。

10. 在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。
    
    <div>
    

    > [!NOTE]  
    > 當您建立或修改轉譯規則時，您都必須執行 [全部認可]<STRONG></STRONG> 命令才能發行組態變更。 如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中使用組建轉譯規則工具建立或修改轉譯規則](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[在 Lync Server 2013 中設定含媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中設定無媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[在 Lync Server 2013 中將擱置的變更發佈至語音路由設定](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

