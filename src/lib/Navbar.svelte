<script>
    import { user } from "../stores";
    import logo from "../assets/todo32.png";

    const msg = "email not found!!";
    const getMail = () => $user.user.email || $user._tokenResponse.email || "email not found!!";

</script>

<nav>
    <div class="w-full flex justify-between px-4 py-2 select-none bg-[#222]">

        <div class="space-x-2 flex-align">
            <span class="object-cover h-4 sm:h-6">
                <img src={logo} alt="logo" class="object-cover h-4 sm:h-6" id="user-image" />
            </span>
            <h1 class="text-lg font-bold leading-normal text-white sm:text-2xl sm:leading-normal">Svelte Todos</h1>
        </div>

        <div class="flex-align group">
            <span class="object-cover w-6 h-6 rounded-full sm:w-10 sm:h-10">
                <img src={$user.user.photoURL} alt="UserImage" class="w-6 h-6 rounded-full cursor-pointer sm:w-10 sm:h-10 userimg"  
                />
            </span>
            
            <div class="hidden group-hover:block z-50 absolute my-4 text-base list-none bg-white divide-y divide-gray-100 rounded-lg shadow dark:bg-gray-700 dark:divide-gray-600 top-[4%] right-[1%] w-52 border border-gray-300">

                <div class="px-4 py-3">
                    <span class="block text-sm text-gray-900 dark:text-white">
                    {$user.user.displayName || $user._tokenResponse.screenName}
                    </span>

                    <span class="block text-sm {getMail() === msg ? 'text-red-500' : 'dark:text-gray-400'} truncate " 
                    title={getMail()}>
                    {getMail()}
                    </span>
                </div>

                <ul class="py-2" aria-labelledby="user-menu-button">
                  <li>
                    <a href={"#"} class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100 dark:hover:bg-gray-600 dark:text-gray-200 dark:hover:text-white">
                        Logout
                    </a>
                  </li>
                </ul>

            </div>
        </div>
    </div>
</nav>