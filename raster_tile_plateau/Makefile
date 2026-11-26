fetch:
	wget https://gsic-opendata.s3.ap-northeast-1.amazonaws.com/national-gov/mlit/city-bureau/3d-city-model/2020/plateau-13213-higashimurayama-shi-2020/ortho/13213_higashimurayama-shi_2020_ortho_3_op.7z
	7z x 13213_higashimurayama-shi_2020_ortho_3_op.7z

buildvrt:
	gdalbuildvrt temp.vrt 13213_higashimurayama-shi_ortho/*.tif

generate_tile:
	gdal2tiles.py --xyz -z 12-18 temp.vrt

deploy:
	sudo cp -r temp/ /opt/niroku/data/plateau/
