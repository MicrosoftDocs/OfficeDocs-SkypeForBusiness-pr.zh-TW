---
title: 在商務用 Skype Server 中將檔案儲存資料移至新的檔案存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 如果您需要移除目前作為商務用 Skype Server 部署之檔案存放區的檔案伺服器，或如果您需要進行其他變更，以使目前的檔案存放庫無法使用，您必須先建立新的共用。 接著，您需要執行下列步驟：
ms.openlocfilehash: 00fa169eb000c9575609359c146a9db24c94de48
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794452"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>在商務用 Skype Server 中將檔案儲存資料移至新的檔案存放區

如果您需要移除目前作為商務用 Skype Server 部署之檔案存放區的檔案伺服器，或如果您需要進行其他變更，以使目前的檔案存放庫無法使用，您必須先建立新的共用。 接著，您需要執行下列步驟：

1. 關閉使用您打算移除之檔案存放區的商務用 Skype 伺服器服務。

2. 在拓撲建立器中定義檔案存放區併發布變更，讓您的部署能使用新的檔案存放區。

3. 將資料移至新的檔存放區。

4. 重新開機伺服器或服務。

5. 或者，移除舊的 [檔案共用] 和 [檔案] 資料夾。

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>將檔案儲存區資料從一個檔案存放區移至新的檔案存放區

1. 以 RTCUniversersalServerAdmins 或 CsServerAdministrator 群組成員的身分登入電腦，其中安裝的是商務用 Skype 伺服器、系統管理工具。

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。

4. 針對每個使用您打算移除之檔案存放區的控制器池、導演、標準版伺服器及前端池，請選取伺服器或池，按一下 [**動作**]，然後按一下 [**停止所有服務**]。

5. 登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。

6. 啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype server**]，然後按一下 [**商務用 skype server 拓撲**建立器]。

7. 選取使用檔案存放區的伺服器或池，然後執行下列動作：

8. 以滑鼠右鍵按一下 [伺服器] 或 [池]，然後按一下 [**編輯屬性**]。

9. 在 [**編輯屬性**] 的 [**關聯**] 底下，按一下 [檔案**存放**] 底下的 [**新增**]。

10. 在 [**定義新檔案存放區**] 的 [檔案**伺服器 FQDN**] 底下，輸入檔案伺服器的完整功能變數名稱（FQDN）。 在 [檔案**共用**] 底下，輸入新檔案共用的資料夾名稱，然後按一下 **[確定]**。

     > [!IMPORTANT]
     > 此步驟會定義要在拓撲建立器中使用的新檔存放區。 您只需定義一次，不能針對每個伺服器定義。 您必須先在已定義的檔案伺服器上建立已定義的檔案共用，才能發佈拓撲。 如需詳細資訊，請參閱[定義前端的檔案存放區](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)。

11. 針對使用檔案存放區的每個伺服器或池，請執行下列動作：

12. 以滑鼠右鍵按一下 [伺服器] 或 [池]，然後按一下 [**編輯屬性**]。

13. 在 [**編輯屬性**] 的 [**關聯**] 底下，選取 [檔案**存放區**] 中的新檔案共用，然後按一下 **[確定]**。

14. 發佈拓撲，檢查 [複製狀態]，然後視需要執行商務用 Skype Server 部署嚮導。 如需詳細資訊，請參閱[移除 Lync server 和元件的一般程式](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)。

15. 啟動命令提示字元：按一下 [**開始**]，按一下 [**執行**]，然後輸入 cmd.exe。

16. 在命令列中，輸入下列內容：

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > /S 開關會複製到檔案、目錄及子目錄中。 /XF 開關會跳過名為「會議」的任何檔案。 使用/MT 開關的 [robocopy] 的目前版本，會以多個執行緒大幅增加複製速度。 如果是/LOG 開關，請使用 C:\Logfiles\log.txt. 形式的目錄路徑和記錄檔案名 這個開關會建立位於指定位置的作業記錄檔。

17. 資料複製完成後，請在 [Lync Server 控制台] 中按一下 [**拓撲**]，然後按一下 [**狀態**]。

18. 針對您停止服務的每個伺服器或池，選取伺服器或池子，按一下 [**動作**]，然後按一下 [**啟動所有服務**]。

19. 從拓撲中移除舊的檔案存放區，然後發佈拓撲。 如需詳細資訊，請參閱[移除檔案存放區](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)。

20. 可選登入包含您剛剛移除為本機管理員群組或網域系統管理員群組成員的檔案存放區的電腦，然後移除舊的檔案共用和目錄。

## <a name="see-also"></a>另請參閱

[將伺服器重新指派至不同的檔案存放區](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[移除檔案存放區](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
