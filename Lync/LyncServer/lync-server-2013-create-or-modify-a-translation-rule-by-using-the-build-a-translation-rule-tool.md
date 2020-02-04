---
title: 使用 [建立翻譯規則] 工具建立或修改翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d45ca4e04146a175ec2782aa798ac27559fce495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>使用 Lync Server 2013 中的 [建立翻譯規則] 工具來建立或修改翻譯規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

如果您想要定義翻譯規則，請在 [**建立翻譯規則**] 工具中輸入一組值，並啟用 Lync Server [控制台] 來為您產生對應的相符模式與翻譯規則，以執行下列步驟。 或者，您也可以手動寫入正則運算式，以定義相符的模式和轉換規則。 如需詳細資訊，請參閱[在 Lync Server 2013 中手動建立或修改翻譯規則](lync-server-2013-create-or-modify-a-translation-rule-manually.md)。

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>使用 [建立翻譯規則] 工具定義規則

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  若要開始定義翻譯規則，請遵循在[Lync server 2013 的 [透過媒體旁路處理] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的步驟，或在 lync server 2013 中的 [透過步驟 9][設定主幹，而不使用 [媒體旁路](lync-server-2013-configure-a-trunk-without-media-bypass.md)]。

4.  在 [**新增翻譯規則**] 或 [**編輯翻譯規則**] 頁面上的 [**名稱**] 底下，輸入描述所翻譯之數位模式的名稱。

5.  可選在 [**描述**] 底下，輸入翻譯規則的描述，例如**美國國際長途撥號**。

6.  在對話方塊的 [**建立翻譯規則**] 區段中，于下欄欄位中輸入值：
    
      - **起始位數**：（選擇性）指定您想要模式符合的前置數位數位。 例如，在這個**+** 欄位中輸入，以符合 e.i 格式（開頭為 +）的數位。
    
      - **長度**：指定 [相符] 模式中的位數，並選取您想要模式與此長度完全相同、至少為此長度或任何長度。 例如，輸入**11** ，然後在下拉式清單中選取 [**至少**]，以符合長度至少為11位數的數位。
    
      - **要移除的位數**：（選用）指定要移除的起始位數數。 例如，輸入**1**來去掉**+** 數位開頭的。
    
      - **要加上的位數**：（選擇性）指定要在已翻譯數位前加上的數位。 例如，如果您想要在套用規則時將011附加到已翻譯的編號中，請輸入**011** 。
    
    您在這些欄位中輸入的值會反映在 [相符] 與 [**翻譯規則**] 欄位的**模式**中。 例如，如果您指定前面的範例值，則在 [模式] 中產生的正則運算式會與 field**相符**：
    
    **^\\+ （\\d{9}\\d +） $**
    
    [**翻譯規則**] 欄位會指定已翻譯數位格式的模式。 此模式有兩個部分：
    
      - 代表 [相符] 模式中之位數的值（例如， **$1**）
    
      - 可選您可以在 [**要新增的數位**] 欄位中輸入的值。
    
    使用上述範例值， **011 $ 1**會出現在 [**翻譯規則**] 欄位中。
    
    套用此翻譯規則時，+ 441235551010 會變成011441235551010。

7.  按一下 **[確定]** 儲存翻譯規則。

8.  按一下 **[確定]** 以儲存幹線設定。

9.  在 [**幹線**設定] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。
    
    <div>
    

    > [!NOTE]
    > 每當您建立或修改翻譯規則時，您必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中手動建立或修改翻譯規則](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
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

