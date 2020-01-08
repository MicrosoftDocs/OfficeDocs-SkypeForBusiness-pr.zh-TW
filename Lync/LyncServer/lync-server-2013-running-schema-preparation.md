---
title: Lync Server 2013：執行架構準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b743e5ef93b14279f5f2f16cb70241617a0c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>在 Lync Server 2013 中執行 Active Directory 架構準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

您可以使用安裝程式或 Lync Server 管理命令介面 Cmdlet 來準備 Active Directory 架構。 擴展 Active Directory 架構的 Cmdlet 是**安裝-CsAdServerSchema**。

<div>


> [!NOTE]  
> 架構準備 Cmdlet （<STRONG>安裝 CsAdServerSchema</STRONG>）必須存取架構主機，這需要遠端登入服務正在執行，且已啟用遠端登入機碼。 如果無法在架構主機上啟用遠端登入服務，您可以在架構主機上本機執行 Cmdlet。 如需有關登錄遠端存取的詳細資料，請參閱 Microsoft 知識庫文章314837：「如何管理對註冊表的遠端存取」 <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>。



</div>

完成架構準備之後，請在繼續進行林準備前，手動確認架構分區已複製。 如需詳細資訊，請參閱[在 Lync Server 2013 中驗證 Active Directory 架構複製](lync-server-2013-verifying-schema-replication.md)。

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>使用安裝程式準備目前林中的架構

1.  以架構管理員群組的成員或架構主機上的系統管理員許可權登入林中的伺服器。

2.  從 Lync Server 2013 安裝資料夾或媒體，執行 setup.exe 以啟動部署嚮導。

3.  如果系統提示您安裝 Microsoft Visual c + + 可轉散發元件，請按一下 **[是]**。

4.  [Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。 選擇預設位置，或**流覽**至您選擇的位置，然後按一下 [**安裝**]。

5.  在 [授權協定] 頁面上，核取 [**我接受授權合約中的條款**]，然後按一下 **[確定]**。

6.  安裝程式會安裝 Lync Server Core 元件。

7.  當 [部署嚮導] 準備好時，請按一下 [**準備 Active Directory**]，然後等待確定部署狀態。

8.  在**步驟1：準備架構**，按一下 [**執行**]。

9.  在 [**準備架構**] 頁面上，按一下 **[下一步]**。

10. 在 [執行命令]**** 頁面上，尋找 [工作狀態：完成]****，然後按一下 [檢視記錄檔]****。

11. 在 [**動作**] 欄底下，展開 [**架構準備**]，尋找每個工作結尾的** \<成功\> **執行結果，以確認架構準備已順利完成，請關閉記錄，然後按一下 **[完成]**。

12. 等待 Active Directory 複製完成，或強制進行複製。

13. 手動確認架構變更已複製到所有其他網網域控制站。 如需詳細資訊，請參閱[在 Lync Server 2013 中驗證 Active Directory 架構複製](lync-server-2013-verifying-schema-replication.md)。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>使用 Cmdlet 準備目前林中的架構

1.  以架構管理員群組的成員的身分登入林中的電腦，以及在架構主機上擁有系統管理員許可權。

2.  安裝 Lync Server Core 元件，如下所示：
    
    1.  從 Lync Server 2013 安裝資料夾或媒體，執行 setup.exe 以啟動 Lync Server 部署嚮導。
    
    2.  如果系統提示您安裝 Microsoft Visual c + + 可轉散發元件，請按一下 **[是]**。
    
    3.  [Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。 選擇預設位置，或**流覽**至您選擇的位置，然後按一下 [**安裝**]。
    
    4.  在 [授權協定] 頁面上，核取 [**我接受授權合約中的條款**]，然後按一下 **[確定]**。 安裝程式會安裝 Lync Server 2013 核心元件。

3.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  用盡
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    如果您沒有指定 Ldf 參數，預設值是從註冊表讀取的 Lync Server 2013 安裝路徑。
    
    例如：
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  使用下列 Cmdlet 來驗證架構準備已完成。
    
        Get-CsAdServerSchema 
    
    如果架構準備成功，此 Cmdlet 會傳回**\_架構版本\_狀態\_** 的值。

6.  等待 Active Directory 複製完成，或強制進行複製。

7.  手動確認架構變更已複製到所有其他網網域控制站。 如需詳細資訊，請參閱[在 Lync Server 2013 中驗證 Active Directory 架構複製](lync-server-2013-verifying-schema-replication.md)。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中驗證 Active Directory 結構描述複寫](lync-server-2013-verifying-schema-replication.md)  


[在 Lync Server 2013 中準備 Active Directory 結構描述](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

