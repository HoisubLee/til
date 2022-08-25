
// 미니 프로젝트와 했던 내용
@Configuration
@EnableWebMvc
public class WebConfig implements WebMvcConfigurer {

    @Override
    public void addCorsMappings(CorsRegistry registry) {
        registry.addMapping("/**")
                .allowedOrigins("http://localhost:3000","https://hanghaeblog-frontend-msf8ybdtm-kwonih1020.vercel.app")
                .allowedMethods("*")
                .allowCredentials(false)
                .maxAge(3000)
                .allowedHeaders("*")
                .exposedHeaders("*");

    }
}


// 클론 코딩 때 했던 내용
@Bean
    public CorsConfigurationSource corsConfigurationSource() {
        CorsConfiguration configuration = new CorsConfiguration();
        // origin
        configuration.setAllowedOriginPatterns(Arrays.asList("*"));
        // method
        configuration.setAllowedMethods(Arrays.asList("*"));
        // header
        configuration.setAllowedHeaders(Arrays.asList("*"));
        configuration.setAllowCredentials(true);

        // header에 토큰 허용
        configuration.addExposedHeader("Authorization");
        configuration.addExposedHeader("RefreshToken");

        UrlBasedCorsConfigurationSource source = new UrlBasedCorsConfigurationSource();
        source.registerCorsConfiguration("/**", configuration);
        return source;
    }