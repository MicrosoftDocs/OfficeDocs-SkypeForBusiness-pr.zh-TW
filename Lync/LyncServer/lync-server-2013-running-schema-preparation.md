---
title: Lync Server 2013：執行架構準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 202052ce01bca6cdc11e8ed36dfede9afba74b8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511100"
---
# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>在 Lync Server 2013 中執行 Active Directory 架構準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

您可以使用安裝程式或 Lync Server 管理命令介面 Cmdlet 來準備 Active Directory 架構。 擴充 Active Directory 架構的指令程式已 **Install-CsAdServerSchema**。

<div>


> [!NOTE]  
> 架構準備指令程式 (<STRONG>Install-CsAdServerSchema</STRONG>) 必須存取架構主機，這需要遠端登入服務執行，且已啟用遠端登入機碼。 如果無法在架構主機上啟用遠端登入服務，您可以在架構主機上以本機方式執行 Cmdlet。 如需有關登錄遠端存取的詳細資訊，請參閱 Microsoft 知識庫文章314837：如何管理登錄的遠端存取，位置是 <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A> 。



</div>

完成架構準備工作之後，請在繼續進行樹系準備之前，手動驗證架構磁碟分割是否已複製。 如需詳細資訊，請參閱 [在 Lync Server 2013 中驗證 Active Directory 架構](lync-server-2013-verifying-schema-replication.md)複寫。

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>若要使用安裝程式來準備目前樹系的架構

1.  以架構管理員群組成員的身分，以架構主機上的系統管理員許可權，登入樹系中的伺服器。

2.  從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動部署嚮導。

3.  如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。

4.  [Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。 請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。

5.  在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。

6.  安裝程式會安裝 Lync Server 核心元件。

7.  當部署嚮導準備好時，請按一下 [ **準備 Active Directory**]，然後等候決定部署狀態。

8.  在 [ **步驟1：準備架構**] 中，按一下 [ **執行**]。

9.  在 [ **準備架構** ] 頁面上，按 **[下一步]**。

10. 在「執行命令」**** 頁面上，尋找 [工作狀態: 已完成]****，然後按一下 [檢視記錄檔]****。

11. 在 [ **動作** ] 欄下，展開 [ **架構準備**]， **\<Success\>** 並在每個工作結束時尋找執行結果，以確認架構準備順利完成，關閉記錄檔，然後按一下 **[完成]**。

12. 等候 Active Directory 複寫完成或強制複寫。

13. 手動驗證架構變更是否已複寫至其他所有的網域控制站。 如需詳細資訊，請參閱 [在 Lync Server 2013 中驗證 Active Directory 架構](lync-server-2013-verifying-schema-replication.md)複寫。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>若要使用 Cmdlet 準備目前樹系的架構

1.  以架構管理員群組成員的身分，以架構主機上的系統管理員許可權，登入樹系中的電腦。

2.  安裝 Lync Server 核心元件，如下所示：
    
    1.  從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署嚮導。
    
    2.  如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。
    
    3.  [Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。 請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。
    
    4.  在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。 安裝程式會安裝 Lync Server 2013 核心元件。

3.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  運行：
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    如果您未指定 Ldf 參數，則預設值為從登錄讀取的 Lync Server 2013 安裝路徑。
    
    例如：
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  使用下列 Cmdlet 來驗證架構準備是否已完成。
    
        Get-CsAdServerSchema 
    
    如果架構準備成功，則此 Cmdlet 會傳回 **架構 \_ 版本 \_ 狀態 \_ ** 的值。

6.  等候 Active Directory 複寫完成或強制複寫。

7.  手動驗證架構變更是否已複寫至其他所有的網域控制站。 如需詳細資訊，請參閱 [在 Lync Server 2013 中驗證 Active Directory 架構](lync-server-2013-verifying-schema-replication.md)複寫。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中驗證 Active Directory 架構複寫](lync-server-2013-verifying-schema-replication.md)  


[在 Lync Server 2013 中準備 Active Directory 架構](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

