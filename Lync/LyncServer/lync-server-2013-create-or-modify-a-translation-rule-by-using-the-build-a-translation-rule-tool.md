---
title: 使用組建轉譯規則工具建立或修改轉譯規則
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
ms.openlocfilehash: 9641170534c4c4ad1ef4976d018699d01d6069a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>在 Lync Server 2013 中使用組建轉譯規則工具建立或修改轉譯規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

若要定義轉譯規則，請在 [**組建轉譯規則**] 工具中輸入一組值，並讓 Lync Server 控制台為您產生對應的符合模式和轉譯規則時，遵循下列步驟。 或者，您可以手動寫入正則運算式，以定義符合的模式和轉譯規則。 如需詳細資訊，請參閱[在 Lync Server 2013 中手動建立或修改轉譯規則](lync-server-2013-create-or-modify-a-translation-rule-manually.md)。

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>使用組建轉譯規則工具定義規則

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  若要開始定義轉譯規則，請遵循在 lync server 2013 中的「透過[媒體旁路」設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的步驟，或在[lync Server 2013 中設定](lync-server-2013-configure-a-trunk-without-media-bypass.md)具有媒體旁路的主幹（透過步驟9）。

4.  在 [**新增轉譯規則**] 或 [**編輯轉譯規則**] 頁面的 [**名稱**] 下，輸入描述所轉譯之號碼模式的名稱。

5.   (選用) 在 [**描述**] 底下，輸入轉譯規則的描述，例如**美國國際長途撥號**。

6.  在對話方塊的 [**組建轉譯規則**] 區段中，于下欄欄位中輸入值：
    
      - **開始位數**： (選用) 指定您想要模式比對的數位前置位數。 例如， **+** 在此欄位中輸入，以比對以 +) 開頭的 (164 格式的數位。
    
      - **Length**：指定比對模式中的位數，並選取是否要讓模式比對此長度的數位完全一致、至少此長度或任何長度。 例如，輸入**11** ，**至少**在下拉式清單中選取，以比對長度至少為11位數的數位。
    
      - **要移除的位數**： (選用) 指定要移除的開始數位的數目。 例如，輸入**1**以 **+** 從號碼的開頭抽出。
    
      - **要新增的位數**： (選用) 指定要預先編號為已轉譯之數位的位數。 例如，如果您希望在套用規則時，將011預先加入翻譯的編號，請輸入**011** 。
    
    您在這些欄位中輸入的值，會反映在 [**要搭配的模式**] 和 [**轉譯規則**] 欄位中。 例如，如果您指定前面的範例值，就會在 [**要搭配的模式**] 欄位中產生正則運算式：
    
    **^\\+ (\\ d {9} \\ d +) $**
    
    **轉譯規則**欄位會指定轉譯後的數位格式的模式。 這種模式分為兩個部分：
    
      - 值 (例如， **$1**) ，代表比對模式中的數位數目
    
      -  (選用) 您可以在 [**要加入的數位**] 欄位中輸入值，以進行前置計算
    
    使用上述範例值， **011 $ 1**會出現在**轉譯規則**欄位中。
    
    套用此轉譯規則時，+ 441235551010 會變成011441235551010。

7.  按一下 ** [確定]** 儲存轉譯規則。

8.  按一下 ** [確定]** 儲存主幹組態。

9.  在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。
    
    <div>
    

    > [!NOTE]
    > 當您建立或修改轉譯規則時，您都必須執行 [全部認可]<STRONG></STRONG> 命令才能發行組態變更。 如需詳細資訊，請參閱 Operations 檔中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A>設定。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中手動建立或修改轉譯規則](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
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

