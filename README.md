<h2>Câu 1:</h2>
    <ul>
      <li>
        UserNamePasswordAuthenticationToken: Đây là một lớp trong Spring
        Security dùng để đại diện cho thông tin đăng nhập của người dùng, bao
        gồm tên đăng nhập (username) và mật khẩu (password). Thông thường, đối
        tượng này được tạo ra sau khi người dùng gửi thông tin đăng nhập từ giao
        diện người dùng lên server.
      </li>
      <li>
        AuthenticationManager: Đây là một giao diện trong Spring Security, đảm
        nhiệm việc xác thực (authentication) đối tượng
        UserNamePasswordAuthenticationToken. Nó nhận vào một đối tượng
        Authentication (bao gồm UserNamePasswordAuthenticationToken) và kiểm tra
        tính hợp lệ của thông tin đăng nhập đó, như kiểm tra tên đăng nhập và
        mật khẩu có chính xác hay không.
      </li>
      <li>
        AuthenticationProvider: Đây là một giao diện trong Spring Security, là
        một thành phần trong AuthenticationManager. Nó có nhiệm vụ xác thực
        người dùng dựa trên các thông tin đăng nhập được cung cấp. Nó có thể hỗ
        trợ nhiều cách xác thực khác nhau, chẳng hạn như xác thực bằng cơ sở dữ
        liệu, xác thực bằng dịch vụ bên ngoài (ví dụ: OAuth),...
      </li>
      <li>
        PasswordEncoder: Đây là một giao diện trong Spring Security, được sử
        dụng để mã hóa mật khẩu của người dùng. Khi người dùng đăng nhập, mật
        khẩu của họ được mã hóa và so sánh với giá trị được lưu trữ trong cơ sở
        dữ liệu hoặc hệ thống xác thực khác.
      </li>
      <li>
        UserDetailsService: Đây là một giao diện trong Spring Security, đảm
        nhiệm việc cung cấp thông tin chi tiết về người dùng, bao gồm tên đăng
        nhập, mật khẩu, vai trò (role) và các thông tin khác, để hỗ trợ xác thực
        người dùng. Nó thường được sử dụng bởi AuthenticationProvider để lấy
        thông tin người dùng từ cơ sở dữ liệu hoặc từ nguồn dữ liệu khác.
      </li>
      <li>
        UserDetails: Đây là một giao diện trong Spring Security, đại diện cho
        chi tiết của một người dùng đã được xác thực. Nó chứa thông tin chi tiết
        về người dùng như tên đăng nhập, mật khẩu đã được mã hóa, vai trò (role)
        và các thông tin khác.
      </li>
    </ul>
    <h2>Câu 2:</h2>
    <ol>
      Workflow trong Spring Security:
      <li>
        Người dùng gửi thông tin đăng nhập từ giao diện người dùng lên server.
      </li>
      <li>
        Thông tin đăng nhập được đóng gói vào một đối tượng
        UserNamePasswordAuthenticationToken.
      </li>
      <li>
        Đối tượng UserNamePasswordAuthenticationToken được truyền vào
        AuthenticationManager để xác thực.
      </li>
      <li>
        AuthenticationManager sử dụng các AuthenticationProvider để xác thực đối
        tượng UserNamePasswordAuthentication
      </li>
    </ol>
    <h2>Câu 3:</h2>
    <h3>
      Session và Cookie là hai khái niệm quan trọng trong việc quản lý trạng
      thái phiên làm việc của người dùng trên web.
    </h3>
    <h4>Session:</h4>
    <ul>
      <li>
        Session là một cơ chế trong công nghệ web dùng để lưu trữ thông tin
        phiên làm việc của người dùng trên máy chủ. Nó tạo ra một phiên làm việc
        riêng biệt cho mỗi người dùng và lưu trữ thông tin trạng thái giữa các
        yêu cầu (request) và phản hồi (response) trên server.
      </li>
      <li>
        Dữ liệu trong session được lưu trữ trên server, thường là trong bộ nhớ,
        và chỉ có thể được truy cập bởi server.
      </li>
      <li>
        Session được quản lý bằng cách gán một mã duy nhất (session ID) cho mỗi
        phiên làm việc của người dùng, và mã này được gửi đến trình duyệt của
        người dùng dưới dạng Cookie hoặc được đính kèm trong URL của các yêu
        cầu.
      </li>
    </ul>
    <h4>Cookie:</h4>
    <li>
      Cookie là một đoạn dữ liệu nhỏ được lưu trữ trên trình duyệt của người
      dùng, được gửi từ máy chủ đến trình duyệt thông qua phản hồi của máy chủ
      và được gửi lại đến máy chủ trong mỗi yêu cầu của người dùng.
    </li>
    <li>
      Dữ liệu trong cookie được lưu trữ trên trình duyệt của người dùng và có
      thể được truy cập và chỉnh sửa bởi mã JavaScript chạy trên trang web hoặc
      bởi server khi yêu cầu được gửi đến.
    </li>
    <li>
      Cookie có thể có thời gian sống (expiration time) để xác định thời gian
      tồn tại của nó trên trình duyệt của người dùng. Nếu không có thời gian
      sống, cookie sẽ tự động bị xóa khi trình duyệt đóng lại.
    </li>
    <h4>Sự khác biệt giữa Session và Cookie:</h4>
    <table>
      <tr>
        <th>Đặc điểm</th>
        <th>Session</th>
        <th>Cookie</th>
      </tr>
      <tr>
        <td>Địa điểm lưu trữ dữ liệu</td>
        <td>Server</td>
        <td>Trình duyệt của người dùng</td>
      </tr>
      <tr>
        <td>Dung lượng lưu trữ</td>
        <td>Không giới hạn (phụ thuộc vào bộ nhớ của máy chủ)</td>
        <td>Giới hạn (thường là dưới 4KB)</td>
      </tr>
      <tr>
        <td>Quản lý dữ liệu</td>
        <td>
          Được quản lý bởi server, không thể truy cập từ mã JavaScript chạy trên
          trang web
        </td>
        <td>Có thể truy cập và chỉnh sửa từ mã JavaScript hoặc server</td>
      </tr>
      <tr>
        <td>Thời gian tồn tại</td>
        <td>Tồn tại trong thời gian phiên làm việc của người dùng</td>
        <td>Có thời gian sống xác định hoặc không có thời gian sống</td>
      </tr>
    </table>
