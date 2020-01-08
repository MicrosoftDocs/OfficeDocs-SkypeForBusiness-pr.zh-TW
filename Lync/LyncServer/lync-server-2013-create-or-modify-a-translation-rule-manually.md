---
title: Lync Server 2013：手動建立或修改翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b17b5a878e066ed0a77c725ae035101d57469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>在 Lync Server 2013 中手動建立或修改翻譯規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-06_

如果您想要定義翻譯規則，方法是撰寫相符模式與翻譯規則的正則運算式，請遵循下列步驟。 或者，您也可以在 [**建立翻譯規則**] 工具中輸入一組值，然後啟用 Lync Server [控制台] 來為您產生對應的相符模式與翻譯規則。 如需詳細資訊，請參閱[使用 Lync Server 2013 中的 [建立翻譯規則] 工具建立或修改翻譯規則](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)。

<div>

## <a name="to-define-a-translation-rule-manually"></a>手動定義翻譯規則

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  若要開始定義翻譯規則，請遵循在[Lync server 2013 的 [透過媒體旁路處理] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的步驟，或在 lync server 2013 中的 [透過步驟 9][設定主幹，而不使用 [媒體旁路](lync-server-2013-configure-a-trunk-without-media-bypass.md)]。

4.  在 [**新增翻譯規則**] 或 [**編輯翻譯規則**] 頁面上的 [**名稱**] 欄位中，輸入描述所翻譯之數位模式的名稱。

5.  可選在 [**描述**] 中，輸入翻譯規則的描述，例如**美國國際長途撥號**。

6.  按一下 [**組建翻譯規則**] 區段底部的 [**編輯**]。

7.  在 [輸入**正則運算式**] 中輸入下列內容：
    
      - 在 [**符合這個模式**] 中，指定將用來符合要翻譯之數位的模式。
    
      - 在**翻譯規則**中，指定翻譯數位格式的模式。
    
    例如，如果您在**翻譯規則**中輸入** ^ \\+ （\\{9}\\d d +） $** **與此模式**和**011 $ 1** ，規則會將 + 441235551010 轉換為011441235551010。

8.  按一下 **[確定]** 儲存翻譯規則。

9.  按一下 **[確定]** 以儲存幹線設定。

10. 在 [**幹線**設定] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。
    
    <div>
    

    > [!NOTE]  
    > 每當您建立或修改翻譯規則時，您必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[使用 Lync Server 2013 中的 [建立翻譯規則] 工具來建立或修改翻譯規則](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中設定沒有媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[在 Lync Server 2013 中發佈語音路由設定的擱置變更](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

